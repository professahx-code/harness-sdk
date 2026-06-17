```ts
type ElicitationContext = RequestHandlerExtra<ClientRequest, ClientNotification>;
```

Defined in: [src/types/elicitation.ts:12](https://github.com/strands-agents/harness-sdk/blob/ba40a091b194165d20cd9270125d792cc647c2dd/strands-ts/src/types/elicitation.ts#L12)

Context provided to an elicitation callback, including the abort signal for the in-flight request.