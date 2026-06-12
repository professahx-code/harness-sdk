```ts
const InvokeModelStage: MiddlewareStage<InvokeModelContext, InvokeModelResult, AgentStreamEvent>;
```

Defined in: [src/middleware/stages.ts:151](https://github.com/strands-agents/harness-sdk/blob/db79d737433905152b5d3dfe9f110fb00f4d2fa6/strands-ts/src/middleware/stages.ts#L151)

Built-in stage wrapping core model invocation. Middleware registered for this stage can rate-limit, cache, or transform model inputs.