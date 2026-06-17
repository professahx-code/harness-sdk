```ts
function toolResultContentFromData(data): ToolResultContent;
```

Defined in: [src/types/messages.ts:432](https://github.com/strands-agents/harness-sdk/blob/d88911386ffd4b5f924c7b896ad24f288632baec/strands-ts/src/types/messages.ts#L432)

Converts a single ToolResultContentData to a ToolResultContent class instance.

## Parameters

| Parameter | Type | Description |
| --- | --- | --- |
| `data` | `ToolResultContentData` | The tool result content data to convert |

## Returns

[`ToolResultContent`](/docs/api/typescript/ToolResultContent/index.md)

A ToolResultContent instance of the appropriate type

## Throws

Error if the content data type is unknown