```ts
type InterruptSource = "tool" | "hook" | "multiagent-hook";
```

Defined in: [src/interrupt.ts:23](https://github.com/strands-agents/harness-sdk/blob/3db1b6375bb18b5c12c42650c6fea93014b9c687/strands-ts/src/interrupt.ts#L23)

Origin of an interrupt:

-   `'tool'` — raised by a tool callback via `ToolContext.interrupt()`.
-   `'hook'` — raised by an agent-level hook (e.g. `BeforeToolCallEvent.interrupt()`).
-   `'multiagent-hook'` — raised by a multi-agent hook (e.g. `BeforeNodeCallEvent.interrupt()`).