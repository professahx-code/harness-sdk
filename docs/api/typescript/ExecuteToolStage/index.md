```ts
const ExecuteToolStage: MiddlewareStage<ExecuteToolContext, ExecuteToolResult, AgentStreamEvent>;
```

Defined in: [src/middleware/stages.ts:161](https://github.com/strands-agents/harness-sdk/blob/d88911386ffd4b5f924c7b896ad24f288632baec/strands-ts/src/middleware/stages.ts#L161)

Built-in stage wrapping individual tool execution. Middleware registered for this stage can add telemetry, validate inputs, or mock responses.