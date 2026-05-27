```ts
type McpTransport = Omit<Transport, "sessionId"> & {
  sessionId?: string;
};
```

Defined in: [src/mcp.ts:29](https://github.com/strands-agents/sdk-typescript/blob/0f99011408c45dcc6ca403794f60c05a1ac61eb8/strands-ts/src/mcp.ts#L29)

Widened transport type that accepts MCP transport implementations without requiring explicit casts.

Under `exactOptionalPropertyTypes`, `StreamableHTTPClientTransport` is not directly assignable to `Transport` because its `sessionId` getter returns `string | undefined`, while `Transport` declares `sessionId?: string` (absent or string, but not explicitly undefined). This type relaxes that constraint so users can pass any MCP transport without `as Transport`.

## Type Declaration

| Name | Type | Defined in |
| --- | --- | --- |
| `sessionId?` | `string` | [src/mcp.ts:29](https://github.com/strands-agents/sdk-typescript/blob/0f99011408c45dcc6ca403794f60c05a1ac61eb8/strands-ts/src/mcp.ts#L29) |