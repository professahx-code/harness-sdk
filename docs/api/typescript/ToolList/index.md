```ts
type ToolList = (
  | Tool
  | McpClient
  | Agent
  | ToolList)[];
```

Defined in: [src/agent/agent.ts:137](https://github.com/strands-agents/harness-sdk/blob/d88911386ffd4b5f924c7b896ad24f288632baec/strands-ts/src/agent/agent.ts#L137)

Recursive type definition for nested tool arrays. Allows tools to be organized in nested arrays of any depth.

[Agent](/docs/api/typescript/Agent/index.md) instances in the array are automatically wrapped via [Agent.asTool](/docs/api/typescript/Agent/index.md#astool), so they can be passed directly without calling `.asTool()` explicitly.