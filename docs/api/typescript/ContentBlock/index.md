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

Defined in: [src/types/messages.ts:160](https://github.com/strands-agents/harness-sdk/blob/d9b9061486aa20414699f47b5b1caddccb3e0dff/strands-ts/src/types/messages.ts#L160)