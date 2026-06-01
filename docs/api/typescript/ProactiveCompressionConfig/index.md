```ts
type ProactiveCompressionConfig = {
  compressionThreshold: number;
};
```

Defined in: [src/conversation-manager/conversation-manager.ts:59](https://github.com/strands-agents/sdk-typescript/blob/e0658993e83c0a615dc91695915f48eda36ba169/strands-ts/src/conversation-manager/conversation-manager.ts#L59)

Configuration for proactive compression when passed as an object.

## Properties

### compressionThreshold

```ts
compressionThreshold: number;
```

Defined in: [src/conversation-manager/conversation-manager.ts:65](https://github.com/strands-agents/sdk-typescript/blob/e0658993e83c0a615dc91695915f48eda36ba169/strands-ts/src/conversation-manager/conversation-manager.ts#L65)

Ratio of context window usage that triggers proactive compression. Value between 0 (exclusive) and 1 (inclusive). Defaults to 0.7 (compress when 70% of the context window is used).