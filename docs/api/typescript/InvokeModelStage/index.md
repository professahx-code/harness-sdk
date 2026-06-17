```ts
const InvokeModelStage: MiddlewareStage<InvokeModelContext, InvokeModelResult, AgentStreamEvent>;
```

Defined in: [src/middleware/stages.ts:155](https://github.com/strands-agents/harness-sdk/blob/278805cd559e63475a4c6f52f52614fffa99e401/strands-ts/src/middleware/stages.ts#L155)

Built-in stage wrapping core model invocation. Middleware registered for this stage can rate-limit, cache, or transform model inputs.