```ts
type McpClientConfig = McpClientOptions & {
  transport?: McpTransport;
  url?: string | URL;
  auth?: McpClientCredentials;
  authProvider?: OAuthClientProvider;
  headers?: Record<string, string>;
};
```

Defined in: [src/mcp.ts:105](https://github.com/strands-agents/sdk-typescript/blob/0f99011408c45dcc6ca403794f60c05a1ac61eb8/strands-ts/src/mcp.ts#L105)

Arguments for configuring an MCP Client.

## Type Declaration

| Name | Type | Description | Defined in |
| --- | --- | --- | --- |
| `transport?` | [`McpTransport`](/docs/api/typescript/McpTransport/index.md) | Pre-constructed transport. Mutually exclusive with `url`. | [src/mcp.ts:107](https://github.com/strands-agents/sdk-typescript/blob/0f99011408c45dcc6ca403794f60c05a1ac61eb8/strands-ts/src/mcp.ts#L107) |
| `url?` | `string` | `URL` | Server URL. When provided, a StreamableHTTP transport is constructed automatically. | [src/mcp.ts:110](https://github.com/strands-agents/sdk-typescript/blob/0f99011408c45dcc6ca403794f60c05a1ac61eb8/strands-ts/src/mcp.ts#L110) |
| `auth?` | [`McpClientCredentials`](/docs/api/typescript/McpClientCredentials/index.md) | Client credentials for OAuth machine-to-machine auth. Requires `url`. | [src/mcp.ts:113](https://github.com/strands-agents/sdk-typescript/blob/0f99011408c45dcc6ca403794f60c05a1ac61eb8/strands-ts/src/mcp.ts#L113) |
| `authProvider?` | `OAuthClientProvider` | Custom OAuth provider for advanced auth flows. Requires `url`. Mutually exclusive with `auth`. | [src/mcp.ts:116](https://github.com/strands-agents/sdk-typescript/blob/0f99011408c45dcc6ca403794f60c05a1ac61eb8/strands-ts/src/mcp.ts#L116) |
| `headers?` | `Record`<`string`, `string`\> | Custom headers to include on every request to the server. Requires `url`. | [src/mcp.ts:119](https://github.com/strands-agents/sdk-typescript/blob/0f99011408c45dcc6ca403794f60c05a1ac61eb8/strands-ts/src/mcp.ts#L119) |