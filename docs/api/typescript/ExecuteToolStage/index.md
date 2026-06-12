```ts
const ExecuteToolStage: MiddlewareStage<ExecuteToolContext, ExecuteToolResult, AgentStreamEvent>;
```

Defined in: [src/middleware/stages.ts:157](https://github.com/strands-agents/harness-sdk/blob/db79d737433905152b5d3dfe9f110fb00f4d2fa6/strands-ts/src/middleware/stages.ts#L157)

Built-in stage wrapping individual tool execution. Middleware registered for this stage can add telemetry, validate inputs, or mock responses.