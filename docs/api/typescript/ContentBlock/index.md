```ts
type ContentBlock =
  | TextBlock
  | ToolUseBlock
  | ToolResultBlock
  | ReasoningBlock
  | CachePointBlock
  | GuardContentBlock
  | ImageBlock
  | VideoBlock
  | DocumentBlock
  | CitationsBlock;
```

Defined in: [src/types/messages.ts:160](https://github.com/strands-agents/harness-sdk/blob/1e560f5e65f4a9458aaf61c65b02c8cb1fe21345/strands-ts/src/types/messages.ts#L160)