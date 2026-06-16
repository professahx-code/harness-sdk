Defined in: [src/models/streaming.ts:472](https://github.com/strands-agents/harness-sdk/blob/49d797ae86485bd24e3e86744b6b959ccc8b9a12/strands-ts/src/models/streaming.ts#L472)

Citations content delta within a content block. Represents a citations content block from the model.

## Properties

### type

```ts
type: "citationsDelta";
```

Defined in: [src/models/streaming.ts:476](https://github.com/strands-agents/harness-sdk/blob/49d797ae86485bd24e3e86744b6b959ccc8b9a12/strands-ts/src/models/streaming.ts#L476)

Discriminator for citations content delta.

---

### citations

```ts
citations: Citation[];
```

Defined in: [src/models/streaming.ts:481](https://github.com/strands-agents/harness-sdk/blob/49d797ae86485bd24e3e86744b6b959ccc8b9a12/strands-ts/src/models/streaming.ts#L481)

Array of citations linking generated content to source locations.

---

### content

```ts
content: CitationGeneratedContent[];
```

Defined in: [src/models/streaming.ts:486](https://github.com/strands-agents/harness-sdk/blob/49d797ae86485bd24e3e86744b6b959ccc8b9a12/strands-ts/src/models/streaming.ts#L486)

The generated content associated with these citations.