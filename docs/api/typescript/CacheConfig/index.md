Defined in: [src/models/model.ts:69](https://github.com/strands-agents/harness-sdk/blob/db79d737433905152b5d3dfe9f110fb00f4d2fa6/strands-ts/src/models/model.ts#L69)

Configuration for prompt caching.

## Extended by

-   [`BedrockCacheConfig`](/docs/api/typescript/BedrockCacheConfig/index.md)

## Properties

### strategy

```ts
strategy: "auto" | "anthropic";
```

Defined in: [src/models/model.ts:76](https://github.com/strands-agents/harness-sdk/blob/db79d737433905152b5d3dfe9f110fb00f4d2fa6/strands-ts/src/models/model.ts#L76)

Caching strategy to use.

-   “auto”: Automatically inject cache points at optimal positions based on model ID detection (after tools, after last user message)
-   “anthropic”: Force enable Anthropic-style caching (useful for application inference profiles)