Defined in: [src/memory/types.ts:195](https://github.com/strands-agents/harness-sdk/blob/3db1b6375bb18b5c12c42650c6fea93014b9c687/strands-ts/src/memory/types.ts#L195)

Configuration for the [MemoryManager](/docs/api/typescript/MemoryManager/index.md).

## Properties

### stores

```ts
stores: MemoryStore[];
```

Defined in: [src/memory/types.ts:197](https://github.com/strands-agents/harness-sdk/blob/3db1b6375bb18b5c12c42650c6fea93014b9c687/strands-ts/src/memory/types.ts#L197)

One or more memory stores to manage.

---

### searchToolConfig?

```ts
optional searchToolConfig?: boolean | MemoryToolConfig;
```

Defined in: [src/memory/types.ts:199](https://github.com/strands-agents/harness-sdk/blob/3db1b6375bb18b5c12c42650c6fea93014b9c687/strands-ts/src/memory/types.ts#L199)

Search tool configuration. Defaults to `true`.

---

### addToolConfig?

```ts
optional addToolConfig?: boolean | MemoryAddToolConfig;
```

Defined in: [src/memory/types.ts:204](https://github.com/strands-agents/harness-sdk/blob/3db1b6375bb18b5c12c42650c6fea93014b9c687/strands-ts/src/memory/types.ts#L204)

Add tool configuration. Defaults to `false` (opt-in). `true` lets the tool write to all writable stores; pass a [MemoryAddToolConfig](/docs/api/typescript/MemoryAddToolConfig/index.md) with `stores` to restrict it to specific ones.