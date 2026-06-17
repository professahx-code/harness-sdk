```ts
type InvokeArgs =
  | string
  | ContentBlock[]
  | ContentBlockData[]
  | Message[]
  | MessageData[]
  | InterruptResponseContent[]
  | InterruptResponseContentData[];
```

Defined in: [src/types/agent.ts:53](https://github.com/strands-agents/harness-sdk/blob/7ac039e427e4b488f61a6af1c827532f46dfffa1/strands-ts/src/types/agent.ts#L53)

Arguments for invoking an agent.

Supports multiple input formats:

-   `string` - User text input (wrapped in TextBlock, creates user Message)
-   `ContentBlock[]` | `ContentBlockData[]` - Array of content blocks (creates single user Message)
-   `Message[]` | `MessageData[]` - Array of messages (appends all to conversation)
-   `InterruptResponseContent[]` - Array of interrupt responses (resumes from interrupted state)