Defined in: [src/memory/types.ts:171](https://github.com/strands-agents/harness-sdk/blob/db79d737433905152b5d3dfe9f110fb00f4d2fa6/strands-ts/src/memory/types.ts#L171)

Options for [MemoryManager.add](/docs/api/typescript/MemoryManager/index.md#add).

## Properties

### metadata?

```ts
optional metadata?: Record<string, JSONValue>;
```

Defined in: [src/memory/types.ts:173](https://github.com/strands-agents/harness-sdk/blob/db79d737433905152b5d3dfe9f110fb00f4d2fa6/strands-ts/src/memory/types.ts#L173)

Metadata to associate with the added entry.

---

### stores?

```ts
optional stores?: string[];
```

Defined in: [src/memory/types.ts:175](https://github.com/strands-agents/harness-sdk/blob/db79d737433905152b5d3dfe9f110fb00f4d2fa6/strands-ts/src/memory/types.ts#L175)

Filter to specific writable stores by name. Omit to write to all writable stores.