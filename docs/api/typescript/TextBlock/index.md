Defined in: [src/types/messages.ts:185](https://github.com/strands-agents/harness-sdk/blob/ef0ed3b3df5c6383d9c6082895aa87e52b2adc1a/strands-ts/src/types/messages.ts#L185)

Text content block within a message.

## Implements

-   [`TextBlockData`](/docs/api/typescript/TextBlockData/index.md)
-   `JSONSerializable`<[`TextBlockData`](/docs/api/typescript/TextBlockData/index.md)\>

## Constructors

### Constructor

```ts
new TextBlock(data): TextBlock;
```

Defined in: [src/types/messages.ts:196](https://github.com/strands-agents/harness-sdk/blob/ef0ed3b3df5c6383d9c6082895aa87e52b2adc1a/strands-ts/src/types/messages.ts#L196)

#### Parameters

| Parameter | Type |
| --- | --- |
| `data` | `string` |

#### Returns

`TextBlock`

## Properties

### type

```ts
readonly type: "textBlock";
```

Defined in: [src/types/messages.ts:189](https://github.com/strands-agents/harness-sdk/blob/ef0ed3b3df5c6383d9c6082895aa87e52b2adc1a/strands-ts/src/types/messages.ts#L189)

Discriminator for text content.

---

### text

```ts
readonly text: string;
```

Defined in: [src/types/messages.ts:194](https://github.com/strands-agents/harness-sdk/blob/ef0ed3b3df5c6383d9c6082895aa87e52b2adc1a/strands-ts/src/types/messages.ts#L194)

Plain text content.

#### Implementation of

[`TextBlockData`](/docs/api/typescript/TextBlockData/index.md).[`text`](/docs/api/typescript/TextBlockData/index.md#text)

## Methods

### toJSON()

```ts
toJSON(): TextBlockData;
```

Defined in: [src/types/messages.ts:204](https://github.com/strands-agents/harness-sdk/blob/ef0ed3b3df5c6383d9c6082895aa87e52b2adc1a/strands-ts/src/types/messages.ts#L204)

Serializes the TextBlock to a JSON-compatible TextBlockData object. Called automatically by JSON.stringify().

#### Returns

[`TextBlockData`](/docs/api/typescript/TextBlockData/index.md)

#### Implementation of

```ts
JSONSerializable.toJSON
```

---

### fromJSON()

```ts
static fromJSON(data): TextBlock;
```

Defined in: [src/types/messages.ts:214](https://github.com/strands-agents/harness-sdk/blob/ef0ed3b3df5c6383d9c6082895aa87e52b2adc1a/strands-ts/src/types/messages.ts#L214)

Creates a TextBlock instance from TextBlockData.

#### Parameters

| Parameter | Type | Description |
| --- | --- | --- |
| `data` | [`TextBlockData`](/docs/api/typescript/TextBlockData/index.md) | TextBlockData to deserialize |

#### Returns

`TextBlock`

TextBlock instance