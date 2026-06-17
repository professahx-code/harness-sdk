```ts
type SystemPromptData = string | SystemContentBlockData[];
```

Defined in: [src/types/messages.ts:719](https://github.com/strands-agents/harness-sdk/blob/1e560f5e65f4a9458aaf61c65b02c8cb1fe21345/strands-ts/src/types/messages.ts#L719)

Data representation of a system prompt. Can be a simple string or an array of system content block data for advanced caching.

This is the data interface counterpart to SystemPrompt, following the “Data” pattern.