```ts
type AgentStreamEvent =
  | ModelStreamUpdateEvent
  | ContentBlockEvent
  | ModelMessageEvent
  | ToolStreamUpdateEvent
  | ToolResultEvent
  | BeforeInvocationEvent
  | AfterInvocationEvent
  | BeforeModelCallEvent
  | AfterModelCallEvent
  | BeforeToolsEvent
  | AfterToolsEvent
  | BeforeToolCallEvent
  | AfterToolCallEvent
  | MessageAddedEvent
  | InterruptEvent
  | AgentResultEvent;
```

Defined in: [src/types/agent.ts:562](https://github.com/strands-agents/harness-sdk/blob/d88911386ffd4b5f924c7b896ad24f288632baec/strands-ts/src/types/agent.ts#L562)

Union type representing all possible streaming events from an agent. This includes model events, tool events, and agent-specific lifecycle events.

This is a discriminated union where each event has a unique type field, allowing for type-safe event handling using switch statements.

Every member extends [HookableEvent](/docs/api/typescript/HookableEvent/index.md) (which extends [StreamEvent](/docs/api/typescript/StreamEvent/index.md)), making all events both streamable and subscribable via hook callbacks. Raw data objects from lower layers (model, tools) should be wrapped in a StreamEvent subclass at the agent boundary rather than added directly.