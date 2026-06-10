Defined in: [src/memory/types.ts:146](https://github.com/strands-agents/harness-sdk/blob/3db1b6375bb18b5c12c42650c6fea93014b9c687/strands-ts/src/memory/types.ts#L146)

Options for [MemoryManager.search](/docs/api/typescript/MemoryManager/index.md#search).

Extends the store primitive [SearchOptions](/docs/api/typescript/SearchOptions/index.md) with manager-level store routing.

## Extends

-   [`SearchOptions`](/docs/api/typescript/SearchOptions/index.md)

## Properties

### maxSearchResults?

```ts
optional maxSearchResults?: number;
```

Defined in: [src/memory/types.ts:33](https://github.com/strands-agents/harness-sdk/blob/3db1b6375bb18b5c12c42650c6fea93014b9c687/strands-ts/src/memory/types.ts#L33)

Maximum number of results to return from this store.

#### Inherited from

[`SearchOptions`](/docs/api/typescript/SearchOptions/index.md).[`maxSearchResults`](/docs/api/typescript/SearchOptions/index.md#maxsearchresults)

---

### stores?

```ts
optional stores?: string[];
```

Defined in: [src/memory/types.ts:148](https://github.com/strands-agents/harness-sdk/blob/3db1b6375bb18b5c12c42650c6fea93014b9c687/strands-ts/src/memory/types.ts#L148)

Filter to specific stores by name. Omit to search all.