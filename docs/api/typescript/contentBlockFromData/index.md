```ts
function contentBlockFromData(data): ContentBlock;
```

Defined in: [src/types/messages.ts:942](https://github.com/strands-agents/harness-sdk/blob/c04fdd821ea0e816a78fdf2e3f95201e3cfa84c5/strands-ts/src/types/messages.ts#L942)

Converts ContentBlockData to a ContentBlock instance. Handles all content block types including text, tool use/result, reasoning, cache points, guard content, and media blocks.

## Parameters

| Parameter | Type | Description |
| --- | --- | --- |
| `data` | [`ContentBlockData`](/docs/api/typescript/ContentBlockData/index.md) | The content block data to convert |

## Returns

[`ContentBlock`](/docs/api/typescript/ContentBlock/index.md)

A ContentBlock instance of the appropriate type

## Throws

Error if the content block type is unknown