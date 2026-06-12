Defined in: [src/models/streaming.ts:296](https://github.com/strands-agents/harness-sdk/blob/db79d737433905152b5d3dfe9f110fb00f4d2fa6/strands-ts/src/models/streaming.ts#L296)

Information about input content redaction. Does not include redactedContent since the original input is already available in the messages array from BeforeModelCallEvent.

## Properties

### replaceContent

```ts
replaceContent: string;
```

Defined in: [src/models/streaming.ts:300](https://github.com/strands-agents/harness-sdk/blob/db79d737433905152b5d3dfe9f110fb00f4d2fa6/strands-ts/src/models/streaming.ts#L300)

The content to replace the redacted input with.