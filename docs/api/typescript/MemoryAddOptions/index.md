Defined in: [src/memory/types.ts:172](https://github.com/strands-agents/harness-sdk/blob/1e560f5e65f4a9458aaf61c65b02c8cb1fe21345/strands-ts/src/memory/types.ts#L172)

Options for [MemoryManager.add](/docs/api/typescript/MemoryManager/index.md#add).

## Properties

### metadata?

```ts
optional metadata?: Record<string, JSONValue>;
```

Defined in: [src/memory/types.ts:174](https://github.com/strands-agents/harness-sdk/blob/1e560f5e65f4a9458aaf61c65b02c8cb1fe21345/strands-ts/src/memory/types.ts#L174)

Metadata to associate with the added entry.

---

### stores?

```ts
optional stores?: string[];
```

Defined in: [src/memory/types.ts:176](https://github.com/strands-agents/harness-sdk/blob/1e560f5e65f4a9458aaf61c65b02c8cb1fe21345/strands-ts/src/memory/types.ts#L176)

Filter to specific writable stores by name. Omit to write to all writable stores.