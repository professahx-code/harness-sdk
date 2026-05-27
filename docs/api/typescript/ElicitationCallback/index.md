```ts
type ElicitationCallback = (context, params) => Promise<ElicitResult>;
```

Defined in: [src/types/elicitation.ts:21](https://github.com/strands-agents/sdk-typescript/blob/0f99011408c45dcc6ca403794f60c05a1ac61eb8/strands-ts/src/types/elicitation.ts#L21)

Callback invoked when an MCP server sends an elicitation request to gather user input during tool execution.

## Parameters

| Parameter | Type | Description |
| --- | --- | --- |
| `context` | [`ElicitationContext`](/docs/api/typescript/ElicitationContext/index.md) | Request context including abort signal. |
| `params` | `ElicitRequestParams` | The elicitation parameters from the server (message, requested schema or URL). |

## Returns

`Promise`<`ElicitResult`\>

The user’s response: accept (with content), decline, or cancel.