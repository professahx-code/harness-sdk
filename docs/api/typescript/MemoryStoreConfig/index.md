Defined in: [src/memory/types.ts:50](https://github.com/strands-agents/harness-sdk/blob/3db1b6375bb18b5c12c42650c6fea93014b9c687/strands-ts/src/memory/types.ts#L50)

Declarative properties shared by every memory store and its config.

This is the single source of truth for a store’s identity and behavior knobs. Both the runtime [MemoryStore](/docs/api/typescript/MemoryStore/index.md) interface and concrete store configs extend it, so these fields are declared once. Concrete stores add their own backend-specific config fields on top.

## Extended by

-   [`MemoryStore`](/docs/api/typescript/MemoryStore/index.md)

## Properties

### name

```ts
readonly name: string;
```

Defined in: [src/memory/types.ts:52](https://github.com/strands-agents/harness-sdk/blob/3db1b6375bb18b5c12c42650c6fea93014b9c687/strands-ts/src/memory/types.ts#L52)

Identifier for this store, used to target specific stores in search/add tools. Must be unique.

---

### description?

```ts
readonly optional description?: string;
```

Defined in: [src/memory/types.ts:54](https://github.com/strands-agents/harness-sdk/blob/3db1b6375bb18b5c12c42650c6fea93014b9c687/strands-ts/src/memory/types.ts#L54)

Human-readable description of what this store contains. Included in tool descriptions.

---

### maxSearchResults?

```ts
readonly optional maxSearchResults?: number;
```

Defined in: [src/memory/types.ts:59](https://github.com/strands-agents/harness-sdk/blob/3db1b6375bb18b5c12c42650c6fea93014b9c687/strands-ts/src/memory/types.ts#L59)

Default maximum number of results this store returns per search, used when a caller does not pass a per-call `maxSearchResults`.

---

### writable?

```ts
readonly optional writable?: boolean;
```

Defined in: [src/memory/types.ts:66](https://github.com/strands-agents/harness-sdk/blob/3db1b6375bb18b5c12c42650c6fea93014b9c687/strands-ts/src/memory/types.ts#L66)

Whether this store accepts writes. Optional at config time (caller intent, defaults to `false`); concrete stores resolve it to a definite boolean on the [MemoryStore](/docs/api/typescript/MemoryStore/index.md) interface.

#### Default Value

```ts
false
```

---

### extraction?

```ts
readonly optional extraction?: ExtractionConfig;
```

Defined in: [src/memory/types.ts:72](https://github.com/strands-agents/harness-sdk/blob/3db1b6375bb18b5c12c42650c6fea93014b9c687/strands-ts/src/memory/types.ts#L72)

Automatic-extraction configuration for this store. When set, the [MemoryManager](/docs/api/typescript/MemoryManager/index.md) runs the configured triggers and writes extracted (or, with no extractor, raw) messages to this store. Requires the store to be writable. Omit for a purely tool-driven store.