```ts
const InvokeModelStage: MiddlewareStage<InvokeModelContext, InvokeModelResult, AgentStreamEvent>;
```

Defined in: [src/middleware/stages.ts:155](https://github.com/strands-agents/harness-sdk/blob/ba40a091b194165d20cd9270125d792cc647c2dd/strands-ts/src/middleware/stages.ts#L155)

Built-in stage wrapping core model invocation. Middleware registered for this stage can rate-limit, cache, or transform model inputs.