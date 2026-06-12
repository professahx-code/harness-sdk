```ts
type ToolExecutorStrategy = "sequential" | "concurrent";
```

Defined in: [src/agent/agent.ts:144](https://github.com/strands-agents/harness-sdk/blob/db79d737433905152b5d3dfe9f110fb00f4d2fa6/strands-ts/src/agent/agent.ts#L144)

Strategy for executing tool calls that the model emits in a single assistant turn.

-   `'concurrent'` (default) — runs all tool calls from a single turn in parallel. Per-tool event order (`BeforeToolCallEvent` → `ToolStreamUpdateEvent*` → `AfterToolCallEvent` → `ToolResultEvent`) is preserved, while cross-tool events may interleave.
-   `'sequential'` — runs tool calls one at a time

Cancellation works identically in both modes: [Agent.cancel](/docs/api/typescript/Agent/index.md#cancel) flips [Agent.cancelSignal](/docs/api/typescript/Agent/index.md#cancelsignal) and tools must observe it cooperatively to stop early. In concurrent mode, prompt batch-wide cancellation requires every in-flight tool to honor the signal.