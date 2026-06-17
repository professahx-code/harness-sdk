```ts
const ExecuteToolStage: MiddlewareStage<ExecuteToolContext, ExecuteToolResult, AgentStreamEvent>;
```

Defined in: [src/middleware/stages.ts:161](https://github.com/strands-agents/harness-sdk/blob/278805cd559e63475a4c6f52f52614fffa99e401/strands-ts/src/middleware/stages.ts#L161)

Built-in stage wrapping individual tool execution. Middleware registered for this stage can add telemetry, validate inputs, or mock responses.