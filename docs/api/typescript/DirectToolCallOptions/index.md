Defined in: [src/agent/tool-caller.ts:25](https://github.com/strands-agents/harness-sdk/blob/d88911386ffd4b5f924c7b896ad24f288632baec/strands-ts/src/agent/tool-caller.ts#L25)

Options for direct tool call execution.

## Properties

### recordDirectToolCall?

```ts
optional recordDirectToolCall?: boolean;
```

Defined in: [src/agent/tool-caller.ts:31](https://github.com/strands-agents/harness-sdk/blob/d88911386ffd4b5f924c7b896ad24f288632baec/strands-ts/src/agent/tool-caller.ts#L31)

Whether to record this tool call in the agent’s message history. Defaults to `true`. Set to `false` to execute the tool without affecting conversation context.