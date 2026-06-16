Defined in: [src/mcp.ts:46](https://github.com/strands-agents/harness-sdk/blob/49d797ae86485bd24e3e86744b6b959ccc8b9a12/strands-ts/src/mcp.ts#L46)

Configuration for MCP task-augmented tool execution.

WARNING: MCP Tasks is an experimental feature in both the MCP specification and this SDK. The API may change without notice in future versions.

When provided to McpClient, enables task-based tool invocation which supports long-running tools with progress tracking. Without this config, tools are called directly without task management.

## Properties

### ttl?

```ts
optional ttl?: number;
```

Defined in: [src/mcp.ts:51](https://github.com/strands-agents/harness-sdk/blob/49d797ae86485bd24e3e86744b6b959ccc8b9a12/strands-ts/src/mcp.ts#L51)

Time-to-live in milliseconds for task polling. Defaults to 60000 (60 seconds).

---

### pollTimeout?

```ts
optional pollTimeout?: number;
```

Defined in: [src/mcp.ts:57](https://github.com/strands-agents/harness-sdk/blob/49d797ae86485bd24e3e86744b6b959ccc8b9a12/strands-ts/src/mcp.ts#L57)

Maximum time in milliseconds to wait for task completion during polling. Defaults to 300000 (5 minutes).