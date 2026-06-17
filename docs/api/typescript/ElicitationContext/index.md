```ts
type ElicitationContext = RequestHandlerExtra<ClientRequest, ClientNotification>;
```

Defined in: [src/types/elicitation.ts:12](https://github.com/strands-agents/harness-sdk/blob/d88911386ffd4b5f924c7b896ad24f288632baec/strands-ts/src/types/elicitation.ts#L12)

Context provided to an elicitation callback, including the abort signal for the in-flight request.