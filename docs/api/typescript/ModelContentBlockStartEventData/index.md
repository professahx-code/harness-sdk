Defined in: [src/models/streaming.ts:85](https://github.com/strands-agents/harness-sdk/blob/d88911386ffd4b5f924c7b896ad24f288632baec/strands-ts/src/models/streaming.ts#L85)

Data for a content block start event.

## Properties

### type

```ts
type: "modelContentBlockStartEvent";
```

Defined in: [src/models/streaming.ts:89](https://github.com/strands-agents/harness-sdk/blob/d88911386ffd4b5f924c7b896ad24f288632baec/strands-ts/src/models/streaming.ts#L89)

Discriminator for content block start events.

---

### start?

```ts
optional start?: ToolUseStart;
```

Defined in: [src/models/streaming.ts:95](https://github.com/strands-agents/harness-sdk/blob/d88911386ffd4b5f924c7b896ad24f288632baec/strands-ts/src/models/streaming.ts#L95)

Information about the content block being started. Only present for tool use blocks.