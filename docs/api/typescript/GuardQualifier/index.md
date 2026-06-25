```ts
type GuardQualifier = "grounding_source" | "query" | "guard_content";
```

Defined in: [src/types/messages.ts:791](https://github.com/strands-agents/harness-sdk/blob/d9b9061486aa20414699f47b5b1caddccb3e0dff/strands-ts/src/types/messages.ts#L791)

Qualifier for guard content. Specifies how the content should be evaluated by guardrails.

-   `grounding_source` - Content to check for grounding/factuality
-   `query` - User query to evaluate
-   `guard_content` - General content for guardrail evaluation