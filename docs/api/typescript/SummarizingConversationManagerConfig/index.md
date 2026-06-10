```ts
type SummarizingConversationManagerConfig = {
  model?: Model;
  summaryRatio?: number;
  preserveRecentMessages?: number;
  summarizationSystemPrompt?: string;
  proactiveCompression?: boolean | ProactiveCompressionConfig;
  pinFirst?: number;
};
```

Defined in: [src/conversation-manager/summarizing-conversation-manager.ts:53](https://github.com/strands-agents/harness-sdk/blob/3db1b6375bb18b5c12c42650c6fea93014b9c687/strands-ts/src/conversation-manager/summarizing-conversation-manager.ts#L53)

Configuration for the summarization conversation manager.

## Properties

### model?

```ts
optional model?: Model;
```

Defined in: [src/conversation-manager/summarizing-conversation-manager.ts:59](https://github.com/strands-agents/harness-sdk/blob/3db1b6375bb18b5c12c42650c6fea93014b9c687/strands-ts/src/conversation-manager/summarizing-conversation-manager.ts#L59)

Model to use for generating summaries. When provided, overrides the model attached to the agent. Useful when you want to use a different model than the one attached to the agent.

---

### summaryRatio?

```ts
optional summaryRatio?: number;
```

Defined in: [src/conversation-manager/summarizing-conversation-manager.ts:65](https://github.com/strands-agents/harness-sdk/blob/3db1b6375bb18b5c12c42650c6fea93014b9c687/strands-ts/src/conversation-manager/summarizing-conversation-manager.ts#L65)

Ratio of messages to summarize when context overflow occurs. Value is clamped to \[0.1, 0.8\]. Defaults to 0.3 (summarize 30% of oldest messages).

---

### preserveRecentMessages?

```ts
optional preserveRecentMessages?: number;
```

Defined in: [src/conversation-manager/summarizing-conversation-manager.ts:71](https://github.com/strands-agents/harness-sdk/blob/3db1b6375bb18b5c12c42650c6fea93014b9c687/strands-ts/src/conversation-manager/summarizing-conversation-manager.ts#L71)

Minimum number of recent messages to always keep. Defaults to 10.

---

### summarizationSystemPrompt?

```ts
optional summarizationSystemPrompt?: string;
```

Defined in: [src/conversation-manager/summarizing-conversation-manager.ts:77](https://github.com/strands-agents/harness-sdk/blob/3db1b6375bb18b5c12c42650c6fea93014b9c687/strands-ts/src/conversation-manager/summarizing-conversation-manager.ts#L77)

Custom system prompt for summarization. If not provided, uses a default prompt that produces structured bullet-point summaries.

---

### proactiveCompression?

```ts
optional proactiveCompression?: boolean | ProactiveCompressionConfig;
```

Defined in: [src/conversation-manager/summarizing-conversation-manager.ts:86](https://github.com/strands-agents/harness-sdk/blob/3db1b6375bb18b5c12c42650c6fea93014b9c687/strands-ts/src/conversation-manager/summarizing-conversation-manager.ts#L86)

Enable proactive context compression before the model call.

-   `true`: compress when 70% of the context window is used (default threshold).
-   `{ compressionThreshold: number }`: compress at the specified ratio (0, 1\].
-   `false` or omitted: disabled, only reactive overflow recovery is used.

---

### pinFirst?

```ts
optional pinFirst?: number;
```

Defined in: [src/conversation-manager/summarizing-conversation-manager.ts:92](https://github.com/strands-agents/harness-sdk/blob/3db1b6375bb18b5c12c42650c6fea93014b9c687/strands-ts/src/conversation-manager/summarizing-conversation-manager.ts#L92)

Number of messages at the start of the conversation to permanently pin. Pinned messages are protected from summarization and compacted to the front.