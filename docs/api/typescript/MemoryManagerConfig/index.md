Defined in: [src/memory/types.ts:212](https://github.com/strands-agents/harness-sdk/blob/db79d737433905152b5d3dfe9f110fb00f4d2fa6/strands-ts/src/memory/types.ts#L212)

Configuration for the [MemoryManager](/docs/api/typescript/MemoryManager/index.md).

## Properties

### stores

```ts
stores: MemoryStore[];
```

Defined in: [src/memory/types.ts:214](https://github.com/strands-agents/harness-sdk/blob/db79d737433905152b5d3dfe9f110fb00f4d2fa6/strands-ts/src/memory/types.ts#L214)

One or more memory stores to manage.

---

### searchToolConfig?

```ts
optional searchToolConfig?: boolean | MemoryToolConfig;
```

Defined in: [src/memory/types.ts:216](https://github.com/strands-agents/harness-sdk/blob/db79d737433905152b5d3dfe9f110fb00f4d2fa6/strands-ts/src/memory/types.ts#L216)

Search tool configuration. Defaults to `true`.

---

### addToolConfig?

```ts
optional addToolConfig?: boolean | MemoryAddToolConfig;
```

Defined in: [src/memory/types.ts:221](https://github.com/strands-agents/harness-sdk/blob/db79d737433905152b5d3dfe9f110fb00f4d2fa6/strands-ts/src/memory/types.ts#L221)

Add tool configuration. Defaults to `false` (opt-in). `true` lets the tool write to all writable stores; pass a [MemoryAddToolConfig](/docs/api/typescript/MemoryAddToolConfig/index.md) with `stores` to restrict it to specific ones.