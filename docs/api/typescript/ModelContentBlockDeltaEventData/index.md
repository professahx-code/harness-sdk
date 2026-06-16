Defined in: [src/models/streaming.ts:123](https://github.com/strands-agents/harness-sdk/blob/49d797ae86485bd24e3e86744b6b959ccc8b9a12/strands-ts/src/models/streaming.ts#L123)

Data for a content block delta event.

## Properties

### type

```ts
type: "modelContentBlockDeltaEvent";
```

Defined in: [src/models/streaming.ts:127](https://github.com/strands-agents/harness-sdk/blob/49d797ae86485bd24e3e86744b6b959ccc8b9a12/strands-ts/src/models/streaming.ts#L127)

Discriminator for content block delta events.

---

### delta

```ts
delta: ContentBlockDelta;
```

Defined in: [src/models/streaming.ts:132](https://github.com/strands-agents/harness-sdk/blob/49d797ae86485bd24e3e86744b6b959ccc8b9a12/strands-ts/src/models/streaming.ts#L132)

The incremental content update.