Defined in: [src/types/messages.ts:464](https://github.com/strands-agents/harness-sdk/blob/ba40a091b194165d20cd9270125d792cc647c2dd/strands-ts/src/types/messages.ts#L464)

Reasoning content block within a message.

## Implements

-   [`ReasoningBlockData`](/docs/api/typescript/ReasoningBlockData/index.md)
-   `JSONSerializable`<{ `reasoning`: `Serialized`<[`ReasoningBlockData`](/docs/api/typescript/ReasoningBlockData/index.md)\>; }>

## Constructors

### Constructor

```ts
new ReasoningBlock(data): ReasoningBlock;
```

Defined in: [src/types/messages.ts:487](https://github.com/strands-agents/harness-sdk/blob/ba40a091b194165d20cd9270125d792cc647c2dd/strands-ts/src/types/messages.ts#L487)

#### Parameters

| Parameter | Type |
| --- | --- |
| `data` | [`ReasoningBlockData`](/docs/api/typescript/ReasoningBlockData/index.md) |

#### Returns

`ReasoningBlock`

## Properties

### type

```ts
readonly type: "reasoningBlock";
```

Defined in: [src/types/messages.ts:470](https://github.com/strands-agents/harness-sdk/blob/ba40a091b194165d20cd9270125d792cc647c2dd/strands-ts/src/types/messages.ts#L470)

Discriminator for reasoning content.

---

### text?

```ts
readonly optional text?: string;
```

Defined in: [src/types/messages.ts:475](https://github.com/strands-agents/harness-sdk/blob/ba40a091b194165d20cd9270125d792cc647c2dd/strands-ts/src/types/messages.ts#L475)

The text content of the reasoning process.

#### Implementation of

[`ReasoningBlockData`](/docs/api/typescript/ReasoningBlockData/index.md).[`text`](/docs/api/typescript/ReasoningBlockData/index.md#text)

---

### signature?

```ts
readonly optional signature?: string;
```

Defined in: [src/types/messages.ts:480](https://github.com/strands-agents/harness-sdk/blob/ba40a091b194165d20cd9270125d792cc647c2dd/strands-ts/src/types/messages.ts#L480)

A cryptographic signature for verification purposes.

#### Implementation of

[`ReasoningBlockData`](/docs/api/typescript/ReasoningBlockData/index.md).[`signature`](/docs/api/typescript/ReasoningBlockData/index.md#signature)

---

### redactedContent?

```ts
readonly optional redactedContent?: Uint8Array;
```

Defined in: [src/types/messages.ts:485](https://github.com/strands-agents/harness-sdk/blob/ba40a091b194165d20cd9270125d792cc647c2dd/strands-ts/src/types/messages.ts#L485)

The redacted content of the reasoning process.

#### Implementation of

[`ReasoningBlockData`](/docs/api/typescript/ReasoningBlockData/index.md).[`redactedContent`](/docs/api/typescript/ReasoningBlockData/index.md#redactedcontent)

## Methods

### toJSON()

```ts
toJSON(): {
  reasoning: {
     text?: string;
     signature?: string;
     redactedContent?: string;
  };
};
```

Defined in: [src/types/messages.ts:504](https://github.com/strands-agents/harness-sdk/blob/ba40a091b194165d20cd9270125d792cc647c2dd/strands-ts/src/types/messages.ts#L504)

Serializes the ReasoningBlock to a JSON-compatible ContentBlockData object. Called automatically by JSON.stringify(). Uint8Array redactedContent is encoded as base64 string.

#### Returns

```ts
{
  reasoning: {
     text?: string;
     signature?: string;
     redactedContent?: string;
  };
}
```

| Name | Type | Description | Defined in |
| --- | --- | --- | --- |
| `reasoning` | { `text?`: `string`; `signature?`: `string`; `redactedContent?`: `string`; } | \- | [src/types/messages.ts:504](https://github.com/strands-agents/harness-sdk/blob/ba40a091b194165d20cd9270125d792cc647c2dd/strands-ts/src/types/messages.ts#L504) |
| `reasoning.text?` | `string` | The text content of the reasoning process. | [src/types/messages.ts:448](https://github.com/strands-agents/harness-sdk/blob/ba40a091b194165d20cd9270125d792cc647c2dd/strands-ts/src/types/messages.ts#L448) |
| `reasoning.signature?` | `string` | A cryptographic signature for verification purposes. | [src/types/messages.ts:453](https://github.com/strands-agents/harness-sdk/blob/ba40a091b194165d20cd9270125d792cc647c2dd/strands-ts/src/types/messages.ts#L453) |
| `reasoning.redactedContent?` | `string` | The redacted content of the reasoning process. | [src/types/messages.ts:458](https://github.com/strands-agents/harness-sdk/blob/ba40a091b194165d20cd9270125d792cc647c2dd/strands-ts/src/types/messages.ts#L458) |

#### Implementation of

```ts
JSONSerializable.toJSON
```

---

### fromJSON()

```ts
static fromJSON(data): ReasoningBlock;
```

Defined in: [src/types/messages.ts:521](https://github.com/strands-agents/harness-sdk/blob/ba40a091b194165d20cd9270125d792cc647c2dd/strands-ts/src/types/messages.ts#L521)

Creates a ReasoningBlock instance from its wrapped data format. Base64-encoded redactedContent is decoded back to Uint8Array.

#### Parameters

| Parameter | Type | Description |
| --- | --- | --- |
| `data` | { `reasoning`: { `text?`: `string`; `signature?`: `string`; `redactedContent?`: `string` | `Uint8Array`<`ArrayBufferLike`\>; }; } | Wrapped ReasoningBlockData to deserialize (accepts both string and Uint8Array for redactedContent) |
| `data.reasoning` | { `text?`: `string`; `signature?`: `string`; `redactedContent?`: `string` | `Uint8Array`<`ArrayBufferLike`\>; } | \- |
| `data.reasoning.text?` | `string` | The text content of the reasoning process. |
| `data.reasoning.signature?` | `string` | A cryptographic signature for verification purposes. |
| `data.reasoning.redactedContent?` | `string` | `Uint8Array`<`ArrayBufferLike`\> | The redacted content of the reasoning process. |

#### Returns

`ReasoningBlock`

ReasoningBlock instance