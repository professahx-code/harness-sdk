```ts
type ContentBlockDelta =
  | TextDelta
  | ToolUseInputDelta
  | ReasoningContentDelta
  | CitationsDelta;
```

Defined in: [src/models/streaming.ts:408](https://github.com/strands-agents/harness-sdk/blob/c04fdd821ea0e816a78fdf2e3f95201e3cfa84c5/strands-ts/src/models/streaming.ts#L408)

A delta (incremental chunk) of content within a content block. Can be text, tool use input, or reasoning content.

This is a discriminated union for type-safe delta handling.