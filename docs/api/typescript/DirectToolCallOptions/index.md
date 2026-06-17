Defined in: [src/agent/tool-caller.ts:25](https://github.com/strands-agents/harness-sdk/blob/ba40a091b194165d20cd9270125d792cc647c2dd/strands-ts/src/agent/tool-caller.ts#L25)

Options for direct tool call execution.

## Properties

### recordDirectToolCall?

```ts
optional recordDirectToolCall?: boolean;
```

Defined in: [src/agent/tool-caller.ts:31](https://github.com/strands-agents/harness-sdk/blob/ba40a091b194165d20cd9270125d792cc647c2dd/strands-ts/src/agent/tool-caller.ts#L31)

Whether to record this tool call in the agent’s message history. Defaults to `true`. Set to `false` to execute the tool without affecting conversation context.