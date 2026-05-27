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

Defined in: [src/types/agent.ts:43](https://github.com/strands-agents/sdk-typescript/blob/0f99011408c45dcc6ca403794f60c05a1ac61eb8/strands-ts/src/types/agent.ts#L43)

Arguments for invoking an agent.

Supports multiple input formats:

-   `string` - User text input (wrapped in TextBlock, creates user Message)
-   `ContentBlock[]` | `ContentBlockData[]` - Array of content blocks (creates single user Message)
-   `Message[]` | `MessageData[]` - Array of messages (appends all to conversation)
-   `InterruptResponseContent[]` - Array of interrupt responses (resumes from interrupted state)