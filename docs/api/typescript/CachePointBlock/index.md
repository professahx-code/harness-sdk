Defined in: [src/types/messages.ts:563](https://github.com/strands-agents/harness-sdk/blob/49d797ae86485bd24e3e86744b6b959ccc8b9a12/strands-ts/src/types/messages.ts#L563)

Cache point block for prompt caching. Marks a position in a message or system prompt where caching should occur.

## Implements

-   [`CachePointBlockData`](/docs/api/typescript/CachePointBlockData/index.md)
-   `JSONSerializable`<{ `cachePoint`: [`CachePointBlockData`](/docs/api/typescript/CachePointBlockData/index.md); }>

## Constructors

### Constructor

```ts
new CachePointBlock(data): CachePointBlock;
```

Defined in: [src/types/messages.ts:580](https://github.com/strands-agents/harness-sdk/blob/49d797ae86485bd24e3e86744b6b959ccc8b9a12/strands-ts/src/types/messages.ts#L580)

#### Parameters

| Parameter | Type |
| --- | --- |
| `data` | [`CachePointBlockData`](/docs/api/typescript/CachePointBlockData/index.md) |

#### Returns

`CachePointBlock`

## Properties

### type

```ts
readonly type: "cachePointBlock";
```

Defined in: [src/types/messages.ts:567](https://github.com/strands-agents/harness-sdk/blob/49d797ae86485bd24e3e86744b6b959ccc8b9a12/strands-ts/src/types/messages.ts#L567)

Discriminator for cache point.

---

### cacheType

```ts
readonly cacheType: "default";
```

Defined in: [src/types/messages.ts:572](https://github.com/strands-agents/harness-sdk/blob/49d797ae86485bd24e3e86744b6b959ccc8b9a12/strands-ts/src/types/messages.ts#L572)

The cache type. Currently only ‘default’ is supported.

#### Implementation of

[`CachePointBlockData`](/docs/api/typescript/CachePointBlockData/index.md).[`cacheType`](/docs/api/typescript/CachePointBlockData/index.md#cachetype)

---

### ttl?

```ts
readonly optional ttl?: string;
```

Defined in: [src/types/messages.ts:578](https://github.com/strands-agents/harness-sdk/blob/49d797ae86485bd24e3e86744b6b959ccc8b9a12/strands-ts/src/types/messages.ts#L578)

Optional TTL for the cache entry. See [CachePointBlockData.ttl](/docs/api/typescript/CachePointBlockData/index.md#ttl) for the provider-specific value space.

#### Implementation of

[`CachePointBlockData`](/docs/api/typescript/CachePointBlockData/index.md).[`ttl`](/docs/api/typescript/CachePointBlockData/index.md#ttl)

## Methods

### toJSON()

```ts
toJSON(): {
  cachePoint: CachePointBlockData;
};
```

Defined in: [src/types/messages.ts:591](https://github.com/strands-agents/harness-sdk/blob/49d797ae86485bd24e3e86744b6b959ccc8b9a12/strands-ts/src/types/messages.ts#L591)

Serializes the CachePointBlock to a JSON-compatible ContentBlockData object. Called automatically by JSON.stringify().

#### Returns

```ts
{
  cachePoint: CachePointBlockData;
}
```

| Name | Type | Defined in |
| --- | --- | --- |
| `cachePoint` | [`CachePointBlockData`](/docs/api/typescript/CachePointBlockData/index.md) | [src/types/messages.ts:591](https://github.com/strands-agents/harness-sdk/blob/49d797ae86485bd24e3e86744b6b959ccc8b9a12/strands-ts/src/types/messages.ts#L591) |

#### Implementation of

```ts
JSONSerializable.toJSON
```

---

### fromJSON()

```ts
static fromJSON(data): CachePointBlock;
```

Defined in: [src/types/messages.ts:606](https://github.com/strands-agents/harness-sdk/blob/49d797ae86485bd24e3e86744b6b959ccc8b9a12/strands-ts/src/types/messages.ts#L606)

Creates a CachePointBlock instance from its wrapped data format.

#### Parameters

| Parameter | Type | Description |
| --- | --- | --- |
| `data` | { `cachePoint`: [`CachePointBlockData`](/docs/api/typescript/CachePointBlockData/index.md); } | Wrapped CachePointBlockData to deserialize |
| `data.cachePoint` | [`CachePointBlockData`](/docs/api/typescript/CachePointBlockData/index.md) | \- |

#### Returns

`CachePointBlock`

CachePointBlock instance