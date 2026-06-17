Defined in: [src/memory/extraction/types.ts:40](https://github.com/strands-agents/harness-sdk/blob/7ac039e427e4b488f61a6af1c827532f46dfffa1/strands-ts/src/memory/extraction/types.ts#L40)

A discrete entry produced by an [Extractor](/docs/api/typescript/Extractor/index.md), ready to be written to a store via its `add`.

## Properties

### content

```ts
content: string;
```

Defined in: [src/memory/extraction/types.ts:42](https://github.com/strands-agents/harness-sdk/blob/7ac039e427e4b488f61a6af1c827532f46dfffa1/strands-ts/src/memory/extraction/types.ts#L42)

The textual content of the entry.

---

### metadata?

```ts
optional metadata?: Record<string, JSONValue>;
```

Defined in: [src/memory/extraction/types.ts:44](https://github.com/strands-agents/harness-sdk/blob/7ac039e427e4b488f61a6af1c827532f46dfffa1/strands-ts/src/memory/extraction/types.ts#L44)

Optional metadata to associate with the entry.