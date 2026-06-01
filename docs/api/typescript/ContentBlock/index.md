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

Defined in: [src/types/messages.ts:153](https://github.com/strands-agents/sdk-typescript/blob/e0658993e83c0a615dc91695915f48eda36ba169/strands-ts/src/types/messages.ts#L153)