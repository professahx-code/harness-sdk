Defined in: [src/memory/extraction/types.ts:123](https://github.com/strands-agents/harness-sdk/blob/3db1b6375bb18b5c12c42650c6fea93014b9c687/strands-ts/src/memory/extraction/types.ts#L123)

Per-store automatic-extraction configuration.

Lives on a store (via [MemoryStoreConfig](/docs/api/typescript/MemoryStoreConfig/index.md)) so different stores can extract on different schedules and in different styles. [trigger](#trigger) decides *when*; [extractor](#extractor) decides *how* (omit it to pass raw messages straight to the store); [filter](#filter) prunes content blocks first.

## Properties

### trigger

```ts
trigger:
  | ExtractionTrigger
  | ExtractionTrigger[];
```

Defined in: [src/memory/extraction/types.ts:128](https://github.com/strands-agents/harness-sdk/blob/3db1b6375bb18b5c12c42650c6fea93014b9c687/strands-ts/src/memory/extraction/types.ts#L128)

When to run extraction. A single trigger or an array; an empty array is rejected at construction. Multiple triggers compose (extraction runs whenever any of them fires).

---

### extractor?

```ts
optional extractor?: Extractor;
```

Defined in: [src/memory/extraction/types.ts:135](https://github.com/strands-agents/harness-sdk/blob/3db1b6375bb18b5c12c42650c6fea93014b9c687/strands-ts/src/memory/extraction/types.ts#L135)

How to turn messages into entries. When set, the store must implement `add` (entries are written to it). When omitted, the manager hands the filtered messages straight to the store’s `addMessages` (which the store must then implement) — so backends that extract server-side need no client-side extractor.

---

### filter?

```ts
optional filter?: MemoryMessageFilter;
```

Defined in: [src/memory/extraction/types.ts:143](https://github.com/strands-agents/harness-sdk/blob/3db1b6375bb18b5c12c42650c6fea93014b9c687/strands-ts/src/memory/extraction/types.ts#L143)

Content blocks to strip before extraction. Defaults to DEFAULT\_MEMORY\_MESSAGE\_FILTER (excludes `toolUse` / `toolResult`).

For use cases or extractors with value in distilling over the *full* turn you instead want everything: pass `{ exclude: [] }` so tool blocks reach `addMessages`.