Defined in: [src/models/streaming.ts:414](https://github.com/strands-agents/harness-sdk/blob/1e560f5e65f4a9458aaf61c65b02c8cb1fe21345/strands-ts/src/models/streaming.ts#L414)

Text delta within a content block. Represents incremental text content from the model.

## Properties

### type

```ts
type: "textDelta";
```

Defined in: [src/models/streaming.ts:418](https://github.com/strands-agents/harness-sdk/blob/1e560f5e65f4a9458aaf61c65b02c8cb1fe21345/strands-ts/src/models/streaming.ts#L418)

Discriminator for text delta.

---

### text

```ts
text: string;
```

Defined in: [src/models/streaming.ts:423](https://github.com/strands-agents/harness-sdk/blob/1e560f5e65f4a9458aaf61c65b02c8cb1fe21345/strands-ts/src/models/streaming.ts#L423)

Incremental text content.