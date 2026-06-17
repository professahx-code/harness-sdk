Defined in: [src/types/messages.ts:330](https://github.com/strands-agents/harness-sdk/blob/278805cd559e63475a4c6f52f52614fffa99e401/strands-ts/src/types/messages.ts#L330)

Data for a tool result block.

## Properties

### toolUseId

```ts
toolUseId: string;
```

Defined in: [src/types/messages.ts:334](https://github.com/strands-agents/harness-sdk/blob/278805cd559e63475a4c6f52f52614fffa99e401/strands-ts/src/types/messages.ts#L334)

The ID of the tool use that this result corresponds to.

---

### status

```ts
status: "success" | "error";
```

Defined in: [src/types/messages.ts:339](https://github.com/strands-agents/harness-sdk/blob/278805cd559e63475a4c6f52f52614fffa99e401/strands-ts/src/types/messages.ts#L339)

Status of the tool execution.

---

### content

```ts
content: ToolResultContentData[];
```

Defined in: [src/types/messages.ts:344](https://github.com/strands-agents/harness-sdk/blob/278805cd559e63475a4c6f52f52614fffa99e401/strands-ts/src/types/messages.ts#L344)

The content returned by the tool.

---

### error?

```ts
optional error?: Error;
```

Defined in: [src/types/messages.ts:351](https://github.com/strands-agents/harness-sdk/blob/278805cd559e63475a4c6f52f52614fffa99e401/strands-ts/src/types/messages.ts#L351)

The original error object when status is ‘error’. Available for inspection by hooks, error handlers, and agent loop. Tools must wrap non-Error thrown values into Error objects.