# Strands ↔ Zouroboros Adapter Design

> **Date:** 2026-06-30  
> **Status:** Design doc — P5 Axis C  
> **Context:** Wrapping Zouroboros swarm executors with Strands hooks for governance

## Problem

Zouroboros swarm executors and Strands agents solve complementary problems:

| System | Strength | Weakness |
|--------|----------|----------|
| **Zouroboros** | Memory + circuit breaking + self-heal + stagnation detection | No runtime hook system for pre/post tool governance |
| **Strands** | Hook pipeline (BeforeToolCall, AfterToolCall, BeforeModelRequest), tool validation, guardrails | No memory system, no circuit breaking |

The adapter layers Strands hooks onto Zouroboros executors *without* modifying either codebase.

## Architecture

```
┌────────────────────────────────────────────────────┐
│                  ZOI Core                           │
│  (routes TQP tasks to correct harness, provides    │
│   DI container for MemoryGate, config)              │
└──────────────────┬─────────────────────────────────┘
                   │
                   ▼
┌────────────────────────────────────────────────────┐
│              Strands Agent (wrapped)                │
│                                                     │
│   Agent.invoke({                                    │
│     tools: [...],                                   │
│     hooks: [BeforeToolCallEvent, AfterToolCallEvent]│
│   })                                                │
│                                                     │
│   ┌─────────────────────────────────────────────┐   │
│   │  Zouroboros Executor                        │   │
│   │  (actual execution logic - unchanged)        │   │
│   └─────────────────────────────────────────────┘   │
└────────────────────────────────────────────────────┘
```

## Implementation Strategy

**Three-tier approach — progressive complexity:**

### Tier 1 — Proxy Adapter (today, $0)
A thin TypeScript wrapper that:
1. Accepts a Zouroboros executor reference
2. Wraps call/exec with Strands hook events
3. Returns Strands Agent-compatible output

No modifications to either codebase. Pure adapter pattern.

### Tier 2 — Strands Hook Consumer (Phase C2)
Zouroboros subscribes to Strands AfterToolUseEvent to capture tool results into its memory episode system. One-way: Strands → Zouroboros.

### Tier 3 — Full Integration (Future)
Both systems share events bidirectionally. Requires ZOI Core maturity.

## Tier 1: Proxy Adapter

```typescript
// Projects/zouroboros/packages/swarm/src/strands-adapter.ts

import type { Agent, Tool, HookEvent } from "strands-ts";

interface StrandsAdapterConfig {
  executor: ZouroborosExecutor;
  tools: Tool[];
  hooks?: HookEvent[];
  memoryGate?: MemoryGate;
}

export class ZouroborosStrandsAdapter {
  private executor: ZouroborosExecutor;
  private tools: Tool[];
  private hooks: HookEvent[];

  constructor(config: StrandsAdapterConfig) {
    this.executor = config.executor;
    this.tools = config.tools;
    this.hooks = config.hooks || [];
  }

  async invoke(input: string): Promise<string> {
    // Pre-hooks
    for (const hook of this.hooks) {
      await hook.beforeModelRequest?.({ input });
    }

    // Delegate to Zouroboros executor
    const result = await this.executor.run(input);

    // Post-hooks
    for (const hook of this.hooks) {
      await hook.afterToolUse?.({ result, tools: this.tools });
    }

    return result;
  }
}
```

## Hook Mapping (Tier 2)

| Strands Event | Zouroboros Consumer | Purpose |
|--------------|---------------------|---------|
| `BeforeToolCallEvent` | Pre-swarm hook (`pre-swarm-hook.sh`) | Tool validation, allow/deny |
| `AfterToolCallEvent` | Memory episode capture | Log tool results to Zouroboros memory |
| `BeforeModelRequestEvent` | Budget check | Circuit breaker state check |

## Files

| Path | Purpose | Phase |
|------|---------|-------|
| `packages/swarm/src/strands-adapter.ts` | Adapter wrapper | C1 |
| `packages/swarm/src/strands-types.ts` | Type definitions | C1 |
| (in strands-ts repo) | (only if we contribute upstream) | C3+ |

## Verification

1. Adapter compiles with TypeScript (`tsc --noEmit`)
2. Adapter wraps a Zouroboros executor and fires BeforeToolCallEvent
3. Tool results are captured as Zouroboros memory episodes

## Decision Record

**Chosen approach: Proxy adapter (Tier 1) over modifying Strands SDK.**
Rationale: Strands is an upstream dependency. Forking or modifying it creates maintenance burden. The adapter pattern gives us 80% of the benefit with 20% of the cost. If Strands hooks prove transformative, we can contribute upstream.
