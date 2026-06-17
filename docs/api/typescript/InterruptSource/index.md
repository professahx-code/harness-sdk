```ts
type InterruptSource = "tool" | "hook" | "middleware" | "multiagent-hook";
```

Defined in: [src/interrupt.ts:23](https://github.com/strands-agents/harness-sdk/blob/d88911386ffd4b5f924c7b896ad24f288632baec/strands-ts/src/interrupt.ts#L23)

Origin of an interrupt:

-   `'tool'` — raised by a tool callback via `ToolContext.interrupt()`.
-   `'hook'` — raised by an agent-level hook (e.g. `BeforeToolCallEvent.interrupt()`).
-   `'multiagent-hook'` — raised by a multi-agent hook (e.g. `BeforeNodeCallEvent.interrupt()`).