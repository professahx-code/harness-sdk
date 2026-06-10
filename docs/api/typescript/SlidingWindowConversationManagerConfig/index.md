```ts
type SlidingWindowConversationManagerConfig = {
  windowSize?: number;
  shouldTruncateResults?: boolean;
  proactiveCompression?: boolean | ProactiveCompressionConfig;
  pinFirst?: number;
};
```

Defined in: [src/conversation-manager/sliding-window-conversation-manager.ts:86](https://github.com/strands-agents/harness-sdk/blob/3db1b6375bb18b5c12c42650c6fea93014b9c687/strands-ts/src/conversation-manager/sliding-window-conversation-manager.ts#L86)

Configuration for the sliding window conversation manager.

## Properties

### windowSize?

```ts
optional windowSize?: number;
```

Defined in: [src/conversation-manager/sliding-window-conversation-manager.ts:91](https://github.com/strands-agents/harness-sdk/blob/3db1b6375bb18b5c12c42650c6fea93014b9c687/strands-ts/src/conversation-manager/sliding-window-conversation-manager.ts#L91)

Maximum number of messages to keep in the conversation history. Defaults to 40 messages.

---

### shouldTruncateResults?

```ts
optional shouldTruncateResults?: boolean;
```

Defined in: [src/conversation-manager/sliding-window-conversation-manager.ts:97](https://github.com/strands-agents/harness-sdk/blob/3db1b6375bb18b5c12c42650c6fea93014b9c687/strands-ts/src/conversation-manager/sliding-window-conversation-manager.ts#L97)

Whether to truncate tool results when a message is too large for the model’s context window. Defaults to true.

---

### proactiveCompression?

```ts
optional proactiveCompression?: boolean | ProactiveCompressionConfig;
```

Defined in: [src/conversation-manager/sliding-window-conversation-manager.ts:106](https://github.com/strands-agents/harness-sdk/blob/3db1b6375bb18b5c12c42650c6fea93014b9c687/strands-ts/src/conversation-manager/sliding-window-conversation-manager.ts#L106)

Enable proactive context compression before the model call.

-   `true`: compress when 70% of the context window is used (default threshold).
-   `{ compressionThreshold: number }`: compress at the specified ratio (0, 1\].
-   `false` or omitted: disabled, only reactive overflow recovery is used.

---

### pinFirst?

```ts
optional pinFirst?: number;
```

Defined in: [src/conversation-manager/sliding-window-conversation-manager.ts:112](https://github.com/strands-agents/harness-sdk/blob/3db1b6375bb18b5c12c42650c6fea93014b9c687/strands-ts/src/conversation-manager/sliding-window-conversation-manager.ts#L112)

Number of messages at the start of the conversation to permanently pin. Pinned messages are protected from eviction during context reduction.