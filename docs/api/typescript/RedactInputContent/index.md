Defined in: [src/models/streaming.ts:296](https://github.com/strands-agents/sdk-typescript/blob/0f99011408c45dcc6ca403794f60c05a1ac61eb8/strands-ts/src/models/streaming.ts#L296)

Information about input content redaction. Does not include redactedContent since the original input is already available in the messages array from BeforeModelCallEvent.

## Properties

### replaceContent

```ts
replaceContent: string;
```

Defined in: [src/models/streaming.ts:300](https://github.com/strands-agents/sdk-typescript/blob/0f99011408c45dcc6ca403794f60c05a1ac61eb8/strands-ts/src/models/streaming.ts#L300)

The content to replace the redacted input with.