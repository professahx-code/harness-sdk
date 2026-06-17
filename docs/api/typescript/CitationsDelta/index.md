Defined in: [src/models/streaming.ts:472](https://github.com/strands-agents/harness-sdk/blob/7ac039e427e4b488f61a6af1c827532f46dfffa1/strands-ts/src/models/streaming.ts#L472)

Citations content delta within a content block. Represents a citations content block from the model.

## Properties

### type

```ts
type: "citationsDelta";
```

Defined in: [src/models/streaming.ts:476](https://github.com/strands-agents/harness-sdk/blob/7ac039e427e4b488f61a6af1c827532f46dfffa1/strands-ts/src/models/streaming.ts#L476)

Discriminator for citations content delta.

---

### citations

```ts
citations: Citation[];
```

Defined in: [src/models/streaming.ts:481](https://github.com/strands-agents/harness-sdk/blob/7ac039e427e4b488f61a6af1c827532f46dfffa1/strands-ts/src/models/streaming.ts#L481)

Array of citations linking generated content to source locations.

---

### content

```ts
content: CitationGeneratedContent[];
```

Defined in: [src/models/streaming.ts:486](https://github.com/strands-agents/harness-sdk/blob/7ac039e427e4b488f61a6af1c827532f46dfffa1/strands-ts/src/models/streaming.ts#L486)

The generated content associated with these citations.