Defined in: [src/memory/types.ts:163](https://github.com/strands-agents/harness-sdk/blob/db79d737433905152b5d3dfe9f110fb00f4d2fa6/strands-ts/src/memory/types.ts#L163)

Options for [MemoryManager.search](/docs/api/typescript/MemoryManager/index.md#search).

Extends the store primitive [SearchOptions](/docs/api/typescript/SearchOptions/index.md) with manager-level store routing.

## Extends

-   [`SearchOptions`](/docs/api/typescript/SearchOptions/index.md)

## Properties

### maxSearchResults?

```ts
optional maxSearchResults?: number;
```

Defined in: [src/memory/types.ts:33](https://github.com/strands-agents/harness-sdk/blob/db79d737433905152b5d3dfe9f110fb00f4d2fa6/strands-ts/src/memory/types.ts#L33)

Maximum number of results to return from this store.

#### Inherited from

[`SearchOptions`](/docs/api/typescript/SearchOptions/index.md).[`maxSearchResults`](/docs/api/typescript/SearchOptions/index.md#maxsearchresults)

---

### stores?

```ts
optional stores?: string[];
```

Defined in: [src/memory/types.ts:165](https://github.com/strands-agents/harness-sdk/blob/db79d737433905152b5d3dfe9f110fb00f4d2fa6/strands-ts/src/memory/types.ts#L165)

Filter to specific stores by name. Omit to search all.