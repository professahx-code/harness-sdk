Defined in: [src/types/messages.ts:249](https://github.com/strands-agents/harness-sdk/blob/7ac039e427e4b488f61a6af1c827532f46dfffa1/strands-ts/src/types/messages.ts#L249)

Tool use content block.

## Implements

-   [`ToolUseBlockData`](/docs/api/typescript/ToolUseBlockData/index.md)
-   `JSONSerializable`<{ `toolUse`: [`ToolUseBlockData`](/docs/api/typescript/ToolUseBlockData/index.md); }>

## Constructors

### Constructor

```ts
new ToolUseBlock(data): ToolUseBlock;
```

Defined in: [src/types/messages.ts:277](https://github.com/strands-agents/harness-sdk/blob/7ac039e427e4b488f61a6af1c827532f46dfffa1/strands-ts/src/types/messages.ts#L277)

#### Parameters

| Parameter | Type |
| --- | --- |
| `data` | [`ToolUseBlockData`](/docs/api/typescript/ToolUseBlockData/index.md) |

#### Returns

`ToolUseBlock`

## Properties

### type

```ts
readonly type: "toolUseBlock";
```

Defined in: [src/types/messages.ts:253](https://github.com/strands-agents/harness-sdk/blob/7ac039e427e4b488f61a6af1c827532f46dfffa1/strands-ts/src/types/messages.ts#L253)

Discriminator for tool use content.

---

### name

```ts
readonly name: string;
```

Defined in: [src/types/messages.ts:258](https://github.com/strands-agents/harness-sdk/blob/7ac039e427e4b488f61a6af1c827532f46dfffa1/strands-ts/src/types/messages.ts#L258)

The name of the tool to execute.

#### Implementation of

[`ToolUseBlockData`](/docs/api/typescript/ToolUseBlockData/index.md).[`name`](/docs/api/typescript/ToolUseBlockData/index.md#name)

---

### toolUseId

```ts
readonly toolUseId: string;
```

Defined in: [src/types/messages.ts:263](https://github.com/strands-agents/harness-sdk/blob/7ac039e427e4b488f61a6af1c827532f46dfffa1/strands-ts/src/types/messages.ts#L263)

Unique identifier for this tool use instance.

#### Implementation of

[`ToolUseBlockData`](/docs/api/typescript/ToolUseBlockData/index.md).[`toolUseId`](/docs/api/typescript/ToolUseBlockData/index.md#tooluseid)

---

### input

```ts
readonly input: JSONValue;
```

Defined in: [src/types/messages.ts:269](https://github.com/strands-agents/harness-sdk/blob/7ac039e427e4b488f61a6af1c827532f46dfffa1/strands-ts/src/types/messages.ts#L269)

The input parameters for the tool. This can be any JSON-serializable value.

#### Implementation of

[`ToolUseBlockData`](/docs/api/typescript/ToolUseBlockData/index.md).[`input`](/docs/api/typescript/ToolUseBlockData/index.md#input)

---

### reasoningSignature?

```ts
readonly optional reasoningSignature?: string;
```

Defined in: [src/types/messages.ts:275](https://github.com/strands-agents/harness-sdk/blob/7ac039e427e4b488f61a6af1c827532f46dfffa1/strands-ts/src/types/messages.ts#L275)

Reasoning signature from thinking models (e.g., Gemini). Must be preserved and sent back to the model for multi-turn tool use.

#### Implementation of

[`ToolUseBlockData`](/docs/api/typescript/ToolUseBlockData/index.md).[`reasoningSignature`](/docs/api/typescript/ToolUseBlockData/index.md#reasoningsignature)

## Methods

### toJSON()

```ts
toJSON(): {
  toolUse: ToolUseBlockData;
};
```

Defined in: [src/types/messages.ts:290](https://github.com/strands-agents/harness-sdk/blob/7ac039e427e4b488f61a6af1c827532f46dfffa1/strands-ts/src/types/messages.ts#L290)

Serializes the ToolUseBlock to a JSON-compatible ContentBlockData object. Called automatically by JSON.stringify().

#### Returns

```ts
{
  toolUse: ToolUseBlockData;
}
```

| Name | Type | Defined in |
| --- | --- | --- |
| `toolUse` | [`ToolUseBlockData`](/docs/api/typescript/ToolUseBlockData/index.md) | [src/types/messages.ts:290](https://github.com/strands-agents/harness-sdk/blob/7ac039e427e4b488f61a6af1c827532f46dfffa1/strands-ts/src/types/messages.ts#L290) |

#### Implementation of

```ts
JSONSerializable.toJSON
```

---

### fromJSON()

```ts
static fromJSON(data): ToolUseBlock;
```

Defined in: [src/types/messages.ts:307](https://github.com/strands-agents/harness-sdk/blob/7ac039e427e4b488f61a6af1c827532f46dfffa1/strands-ts/src/types/messages.ts#L307)

Creates a ToolUseBlock instance from its wrapped data format.

#### Parameters

| Parameter | Type | Description |
| --- | --- | --- |
| `data` | { `toolUse`: [`ToolUseBlockData`](/docs/api/typescript/ToolUseBlockData/index.md); } | Wrapped ToolUseBlockData to deserialize |
| `data.toolUse` | [`ToolUseBlockData`](/docs/api/typescript/ToolUseBlockData/index.md) | \- |

#### Returns

`ToolUseBlock`

ToolUseBlock instance