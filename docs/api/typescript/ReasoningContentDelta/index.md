Defined in: [src/models/streaming.ts:446](https://github.com/strands-agents/harness-sdk/blob/3db1b6375bb18b5c12c42650c6fea93014b9c687/strands-ts/src/models/streaming.ts#L446)

Reasoning content delta within a content block. Represents incremental reasoning or thinking content.

## Properties

### type

```ts
type: "reasoningContentDelta";
```

Defined in: [src/models/streaming.ts:450](https://github.com/strands-agents/harness-sdk/blob/3db1b6375bb18b5c12c42650c6fea93014b9c687/strands-ts/src/models/streaming.ts#L450)

Discriminator for reasoning delta.

---

### text?

```ts
optional text?: string;
```

Defined in: [src/models/streaming.ts:455](https://github.com/strands-agents/harness-sdk/blob/3db1b6375bb18b5c12c42650c6fea93014b9c687/strands-ts/src/models/streaming.ts#L455)

Incremental reasoning text.

---

### signature?

```ts
optional signature?: string;
```

Defined in: [src/models/streaming.ts:460](https://github.com/strands-agents/harness-sdk/blob/3db1b6375bb18b5c12c42650c6fea93014b9c687/strands-ts/src/models/streaming.ts#L460)

Incremental signature data.

---

### redactedContent?

```ts
optional redactedContent?: Uint8Array;
```

Defined in: [src/models/streaming.ts:465](https://github.com/strands-agents/harness-sdk/blob/3db1b6375bb18b5c12c42650c6fea93014b9c687/strands-ts/src/models/streaming.ts#L465)

Incremental redacted content data.