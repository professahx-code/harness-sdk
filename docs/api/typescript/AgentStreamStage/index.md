```ts
const AgentStreamStage: MiddlewareStage<AgentStreamContext, AgentStreamResult, AgentStreamEvent>;
```

Defined in: [src/middleware/stages.ts:163](https://github.com/strands-agents/harness-sdk/blob/db79d737433905152b5d3dfe9f110fb00f4d2fa6/strands-ts/src/middleware/stages.ts#L163)

Built-in stage wrapping the entire agent output stream. Middleware registered for this stage can filter, transform, or inject events.