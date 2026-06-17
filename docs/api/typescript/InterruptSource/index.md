```ts
type InterruptSource = "tool" | "hook" | "middleware" | "multiagent-hook";
```

Defined in: [src/interrupt.ts:23](https://github.com/strands-agents/harness-sdk/blob/1e560f5e65f4a9458aaf61c65b02c8cb1fe21345/strands-ts/src/interrupt.ts#L23)

Origin of an interrupt:

-   `'tool'` — raised by a tool callback via `ToolContext.interrupt()`.
-   `'hook'` — raised by an agent-level hook (e.g. `BeforeToolCallEvent.interrupt()`).
-   `'multiagent-hook'` — raised by a multi-agent hook (e.g. `BeforeNodeCallEvent.interrupt()`).