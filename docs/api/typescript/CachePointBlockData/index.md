Defined in: [src/types/messages.ts:543](https://github.com/strands-agents/harness-sdk/blob/7ac039e427e4b488f61a6af1c827532f46dfffa1/strands-ts/src/types/messages.ts#L543)

Data for a cache point block.

## Properties

### cacheType

```ts
cacheType: "default";
```

Defined in: [src/types/messages.ts:547](https://github.com/strands-agents/harness-sdk/blob/7ac039e427e4b488f61a6af1c827532f46dfffa1/strands-ts/src/types/messages.ts#L547)

The cache type. Currently only ‘default’ is supported.

---

### ttl?

```ts
optional ttl?: string;
```

Defined in: [src/types/messages.ts:556](https://github.com/strands-agents/harness-sdk/blob/7ac039e427e4b488f61a6af1c827532f46dfffa1/strands-ts/src/types/messages.ts#L556)

Optional TTL for the cache entry. When omitted, the provider’s default TTL is used.

The accepted value space is provider-specific. For example, the Bedrock provider only accepts the values defined by `BedrockCacheTTL` (`'5m'` and `'1h'`). Other providers may accept different values or ignore this field.