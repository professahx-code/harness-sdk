Defined in: [src/sandbox/base.ts:14](https://github.com/strands-agents/sdk-typescript/blob/0f99011408c45dcc6ca403794f60c05a1ac61eb8/strands-ts/src/sandbox/base.ts#L14)

Options for command and code execution.

## Properties

### timeout?

```ts
optional timeout?: number;
```

Defined in: [src/sandbox/base.ts:16](https://github.com/strands-agents/sdk-typescript/blob/0f99011408c45dcc6ca403794f60c05a1ac61eb8/strands-ts/src/sandbox/base.ts#L16)

Maximum execution time in seconds. `undefined` means no timeout.

---

### cwd?

```ts
optional cwd?: string;
```

Defined in: [src/sandbox/base.ts:18](https://github.com/strands-agents/sdk-typescript/blob/0f99011408c45dcc6ca403794f60c05a1ac61eb8/strands-ts/src/sandbox/base.ts#L18)

Working directory for execution. `undefined` means use the sandbox default.

---

### signal?

```ts
optional signal?: AbortSignal;
```

Defined in: [src/sandbox/base.ts:20](https://github.com/strands-agents/sdk-typescript/blob/0f99011408c45dcc6ca403794f60c05a1ac61eb8/strands-ts/src/sandbox/base.ts#L20)

Abort signal to cancel execution. The process is killed when the signal fires.