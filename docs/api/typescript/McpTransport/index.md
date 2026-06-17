```ts
type McpTransport = Omit<Transport, "sessionId"> & {
  sessionId?: string;
};
```

Defined in: [src/mcp.ts:28](https://github.com/strands-agents/harness-sdk/blob/d88911386ffd4b5f924c7b896ad24f288632baec/strands-ts/src/mcp.ts#L28)

Widened transport type that accepts MCP transport implementations without requiring explicit casts.

Under `exactOptionalPropertyTypes`, `StreamableHTTPClientTransport` is not directly assignable to `Transport` because its `sessionId` getter returns `string | undefined`, while `Transport` declares `sessionId?: string` (absent or string, but not explicitly undefined). This type relaxes that constraint so users can pass any MCP transport without `as Transport`.

## Type Declaration

| Name | Type | Defined in |
| --- | --- | --- |
| `sessionId?` | `string` | [src/mcp.ts:28](https://github.com/strands-agents/harness-sdk/blob/d88911386ffd4b5f924c7b896ad24f288632baec/strands-ts/src/mcp.ts#L28) |