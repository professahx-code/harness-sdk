Defined in: [src/sandbox/base.ts:14](https://github.com/strands-agents/harness-sdk/blob/3db1b6375bb18b5c12c42650c6fea93014b9c687/strands-ts/src/sandbox/base.ts#L14)

Options for command and code execution.

## Properties

### timeout?

```ts
optional timeout?: number;
```

Defined in: [src/sandbox/base.ts:16](https://github.com/strands-agents/harness-sdk/blob/3db1b6375bb18b5c12c42650c6fea93014b9c687/strands-ts/src/sandbox/base.ts#L16)

Maximum execution time in seconds. `undefined` means no timeout.

---

### cwd?

```ts
optional cwd?: string;
```

Defined in: [src/sandbox/base.ts:18](https://github.com/strands-agents/harness-sdk/blob/3db1b6375bb18b5c12c42650c6fea93014b9c687/strands-ts/src/sandbox/base.ts#L18)

Working directory for execution. `undefined` means use the sandbox default.

---

### signal?

```ts
optional signal?: AbortSignal;
```

Defined in: [src/sandbox/base.ts:20](https://github.com/strands-agents/harness-sdk/blob/3db1b6375bb18b5c12c42650c6fea93014b9c687/strands-ts/src/sandbox/base.ts#L20)

Abort signal to cancel execution. The process is killed when the signal fires.

---

### env?

```ts
optional env?: Record<string, string>;
```

Defined in: [src/sandbox/base.ts:26](https://github.com/strands-agents/harness-sdk/blob/3db1b6375bb18b5c12c42650c6fea93014b9c687/strands-ts/src/sandbox/base.ts#L26)

Environment variables to set for this command. Built-in sandboxes always apply these, though the mechanism differs (Docker `-e` flags, SSH `env` prefix); custom `Sandbox` implementations must handle env explicitly or it has no effect.