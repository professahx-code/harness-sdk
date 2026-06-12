Defined in: [src/memory/types.ts:9](https://github.com/strands-agents/harness-sdk/blob/db79d737433905152b5d3dfe9f110fb00f4d2fa6/strands-ts/src/memory/types.ts#L9)

A single memory entry retrieved from or stored to a memory store.

## Properties

### content

```ts
content: string;
```

Defined in: [src/memory/types.ts:11](https://github.com/strands-agents/harness-sdk/blob/db79d737433905152b5d3dfe9f110fb00f4d2fa6/strands-ts/src/memory/types.ts#L11)

The textual content of this memory entry.

---

### storeName?

```ts
optional storeName?: string;
```

Defined in: [src/memory/types.ts:17](https://github.com/strands-agents/harness-sdk/blob/db79d737433905152b5d3dfe9f110fb00f4d2fa6/strands-ts/src/memory/types.ts#L17)

Name of the store this entry came from. Populated by [MemoryManager.search](/docs/api/typescript/MemoryManager/index.md#search) so callers (and the model, via `search_memory`) can tell which store produced each result and refine targeting. Stores need not set this themselves.

---

### metadata?

```ts
optional metadata?: Record<string, JSONValue>;
```

Defined in: [src/memory/types.ts:19](https://github.com/strands-agents/harness-sdk/blob/db79d737433905152b5d3dfe9f110fb00f4d2fa6/strands-ts/src/memory/types.ts#L19)

Optional metadata (e.g., score, source, id, timestamp).