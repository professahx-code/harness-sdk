Defined in: [src/agent/tool-caller.ts:25](https://github.com/strands-agents/sdk-typescript/blob/e0658993e83c0a615dc91695915f48eda36ba169/strands-ts/src/agent/tool-caller.ts#L25)

Options for direct tool call execution.

## Properties

### recordDirectToolCall?

```ts
optional recordDirectToolCall?: boolean;
```

Defined in: [src/agent/tool-caller.ts:31](https://github.com/strands-agents/sdk-typescript/blob/e0658993e83c0a615dc91695915f48eda36ba169/strands-ts/src/agent/tool-caller.ts#L31)

Whether to record this tool call in the agent’s message history. Defaults to `true`. Set to `false` to execute the tool without affecting conversation context.