Defined in: [src/memory/types.ts:83](https://github.com/strands-agents/harness-sdk/blob/3db1b6375bb18b5c12c42650c6fea93014b9c687/strands-ts/src/memory/types.ts#L83)

Interface for a memory store backend.

Extends [MemoryStoreConfig](/docs/api/typescript/MemoryStoreConfig/index.md) with the runtime methods a store provides. Every store is searchable; the resolved `writable` flag declares whether it also accepts writes, which is how the [MemoryManager](/docs/api/typescript/MemoryManager/index.md) decides where to route them. `search_memory` can query all stores, while `add_memory` can only write to `writable` stores.

## Extends

-   [`MemoryStoreConfig`](/docs/api/typescript/MemoryStoreConfig/index.md)

## Properties

### name

```ts
readonly name: string;
```

Defined in: [src/memory/types.ts:52](https://github.com/strands-agents/harness-sdk/blob/3db1b6375bb18b5c12c42650c6fea93014b9c687/strands-ts/src/memory/types.ts#L52)

Identifier for this store, used to target specific stores in search/add tools. Must be unique.

#### Inherited from

[`MemoryStoreConfig`](/docs/api/typescript/MemoryStoreConfig/index.md).[`name`](/docs/api/typescript/MemoryStoreConfig/index.md#name)

---

### description?

```ts
readonly optional description?: string;
```

Defined in: [src/memory/types.ts:54](https://github.com/strands-agents/harness-sdk/blob/3db1b6375bb18b5c12c42650c6fea93014b9c687/strands-ts/src/memory/types.ts#L54)

Human-readable description of what this store contains. Included in tool descriptions.

#### Inherited from

[`MemoryStoreConfig`](/docs/api/typescript/MemoryStoreConfig/index.md).[`description`](/docs/api/typescript/MemoryStoreConfig/index.md#description)

---

### maxSearchResults?

```ts
readonly optional maxSearchResults?: number;
```

Defined in: [src/memory/types.ts:59](https://github.com/strands-agents/harness-sdk/blob/3db1b6375bb18b5c12c42650c6fea93014b9c687/strands-ts/src/memory/types.ts#L59)

Default maximum number of results this store returns per search, used when a caller does not pass a per-call `maxSearchResults`.

#### Inherited from

[`MemoryStoreConfig`](/docs/api/typescript/MemoryStoreConfig/index.md).[`maxSearchResults`](/docs/api/typescript/MemoryStoreConfig/index.md#maxsearchresults)

---

### extraction?

```ts
readonly optional extraction?: ExtractionConfig;
```

Defined in: [src/memory/types.ts:72](https://github.com/strands-agents/harness-sdk/blob/3db1b6375bb18b5c12c42650c6fea93014b9c687/strands-ts/src/memory/types.ts#L72)

Automatic-extraction configuration for this store. When set, the [MemoryManager](/docs/api/typescript/MemoryManager/index.md) runs the configured triggers and writes extracted (or, with no extractor, raw) messages to this store. Requires the store to be writable. Omit for a purely tool-driven store.

#### Inherited from

[`MemoryStoreConfig`](/docs/api/typescript/MemoryStoreConfig/index.md).[`extraction`](/docs/api/typescript/MemoryStoreConfig/index.md#extraction)

---

### writable

```ts
readonly writable: boolean;
```

Defined in: [src/memory/types.ts:90](https://github.com/strands-agents/harness-sdk/blob/3db1b6375bb18b5c12c42650c6fea93014b9c687/strands-ts/src/memory/types.ts#L90)

Whether this store accepts writes.

-   `false`: searchable only; never written to.
-   `true`: searchable and writable. Requires at least one write sink — `add`, `addMessages`, or both — to be implemented.

#### Overrides

[`MemoryStoreConfig`](/docs/api/typescript/MemoryStoreConfig/index.md).[`writable`](/docs/api/typescript/MemoryStoreConfig/index.md#writable)

## Methods

### search()

```ts
search(query, options?): Promise<MemoryEntry[]>;
```

Defined in: [src/memory/types.ts:92](https://github.com/strands-agents/harness-sdk/blob/3db1b6375bb18b5c12c42650c6fea93014b9c687/strands-ts/src/memory/types.ts#L92)

Search the store for entries matching the query, ordered by relevance.

#### Parameters

| Parameter | Type |
| --- | --- |
| `query` | `string` |
| `options?` | [`SearchOptions`](/docs/api/typescript/SearchOptions/index.md) |

#### Returns

`Promise`<[`MemoryEntry`](/docs/api/typescript/MemoryEntry/index.md)\[\]>

---

### add()?

```ts
optional add(content, metadata?): Promise<unknown>;
```

Defined in: [src/memory/types.ts:109](https://github.com/strands-agents/harness-sdk/blob/3db1b6375bb18b5c12c42650c6fea93014b9c687/strands-ts/src/memory/types.ts#L109)

Add a single piece of content to the store. Used by the `add_memory` tool, the programmatic [MemoryManager.add](/docs/api/typescript/MemoryManager/index.md#add), and by extraction when an [ExtractionConfig.extractor](/docs/api/typescript/ExtractionConfig/index.md#extractor) produces discrete entries (an extraction config with an extractor requires this method).

A store satisfies `writable: true` with `add`, [addMessages](#addmessages), or both. A store may also implement `add` while declaring `writable: false`, in which case it is never invoked.

Extraction writes are at-least-once: if one entry in a batch fails, the whole batch is retried, so `add` may be called again with content it already stored. Implementations used with extraction should tolerate duplicate writes (e.g. dedupe, or accept that retries may re-store an entry).

The resolved value is store-specific (e.g. a created record id or a write receipt) — each backend may return whatever shape fits it. The [MemoryManager](/docs/api/typescript/MemoryManager/index.md) does not consume this value (it only awaits completion); callers using a store directly can read it.

#### Parameters

| Parameter | Type |
| --- | --- |
| `content` | `string` |
| `metadata?` | `Record`<`string`, [`JSONValue`](/docs/api/typescript/JSONValue/index.md)\> |

#### Returns

`Promise`<`unknown`\>

---

### addMessages()?

```ts
optional addMessages(messages, context?): Promise<unknown>;
```

Defined in: [src/memory/types.ts:129](https://github.com/strands-agents/harness-sdk/blob/3db1b6375bb18b5c12c42650c6fea93014b9c687/strands-ts/src/memory/types.ts#L129)

Ingest a batch of conversation messages, preserving their role structure. This is the sink for automatic extraction that does not distill facts client-side: the manager hands the filtered [MessageData](/docs/api/typescript/MessageData/index.md) batch straight here in one call — no serialization, no model call. Backends that turn raw turns into memory themselves (e.g. role-aware conversational APIs that summarize server-side) implement this so the user/assistant structure survives. A store using extraction implements this method, unless it configures an [ExtractionConfig.extractor](/docs/api/typescript/ExtractionConfig/index.md#extractor) (which produces discrete entries written via [add](#add) instead).

Satisfies `writable: true` the same way [add](#add) does. The resolved value is store-specific and not consumed by the manager.

A store scopes its writes (e.g. by tenant or namespace) through its own configuration. The [AddMessagesContext](/docs/api/typescript/AddMessagesContext/index.md) parameter lets the manager pass additional per-batch context to the store.

#### Parameters

| Parameter | Type | Description |
| --- | --- | --- |
| `messages` | [`MessageData`](/docs/api/typescript/MessageData/index.md)\[\] | The filtered messages to ingest, in order |
| `context?` | [`AddMessagesContext`](/docs/api/typescript/AddMessagesContext/index.md) | Manager-supplied per-batch context (see [AddMessagesContext](/docs/api/typescript/AddMessagesContext/index.md)) |

#### Returns

`Promise`<`unknown`\>

---

### getTools()?

```ts
optional getTools(): Tool[];
```

Defined in: [src/memory/types.ts:138](https://github.com/strands-agents/harness-sdk/blob/3db1b6375bb18b5c12c42650c6fea93014b9c687/strands-ts/src/memory/types.ts#L138)

Returns store-specific tools to register with the agent, through a [MemoryManager](/docs/api/typescript/MemoryManager/index.md). Registers tools alongside `search_memory` / `add_memory` tools if enabled on the [MemoryManager](/docs/api/typescript/MemoryManager/index.md). Implement to expose backend-specific capabilities (e.g. a store-native query tool). Optional, mirrors [Plugin.getTools](/docs/api/typescript/Plugin/index.md#gettools).

#### Returns

[`Tool`](/docs/api/typescript/Tool/index.md)\[\]

Array of tools provided by this store