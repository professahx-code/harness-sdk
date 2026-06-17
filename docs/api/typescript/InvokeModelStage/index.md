```ts
const InvokeModelStage: MiddlewareStage<InvokeModelContext, InvokeModelResult, AgentStreamEvent>;
```

Defined in: [src/middleware/stages.ts:155](https://github.com/strands-agents/harness-sdk/blob/d88911386ffd4b5f924c7b896ad24f288632baec/strands-ts/src/middleware/stages.ts#L155)

Built-in stage wrapping core model invocation. Middleware registered for this stage can rate-limit, cache, or transform model inputs.