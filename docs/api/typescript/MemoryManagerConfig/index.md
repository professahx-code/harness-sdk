Defined in: [src/memory/types.ts:258](https://github.com/strands-agents/harness-sdk/blob/c04fdd821ea0e816a78fdf2e3f95201e3cfa84c5/strands-ts/src/memory/types.ts#L258)

Configuration for the [MemoryManager](/docs/api/typescript/MemoryManager/index.md).

## Properties

### stores

```ts
stores: MemoryStore[];
```

Defined in: [src/memory/types.ts:260](https://github.com/strands-agents/harness-sdk/blob/c04fdd821ea0e816a78fdf2e3f95201e3cfa84c5/strands-ts/src/memory/types.ts#L260)

One or more memory stores to manage.

---

### searchToolConfig?

```ts
optional searchToolConfig?: boolean | MemoryToolConfig;
```

Defined in: [src/memory/types.ts:262](https://github.com/strands-agents/harness-sdk/blob/c04fdd821ea0e816a78fdf2e3f95201e3cfa84c5/strands-ts/src/memory/types.ts#L262)

Search tool configuration. Defaults to `true`.

---

### addToolConfig?

```ts
optional addToolConfig?: boolean | MemoryAddToolConfig;
```

Defined in: [src/memory/types.ts:267](https://github.com/strands-agents/harness-sdk/blob/c04fdd821ea0e816a78fdf2e3f95201e3cfa84c5/strands-ts/src/memory/types.ts#L267)

Add tool configuration. Defaults to `false` (opt-in). `true` lets the tool write to all writable stores; pass a [MemoryAddToolConfig](/docs/api/typescript/MemoryAddToolConfig/index.md) with `stores` to restrict it to specific ones.

---

### injection?

```ts
optional injection?: boolean | MemoryInjectionConfig;
```

Defined in: [src/memory/types.ts:283](https://github.com/strands-agents/harness-sdk/blob/c04fdd821ea0e816a78fdf2e3f95201e3cfa84c5/strands-ts/src/memory/types.ts#L283)

Memory context injection. Defaults to `true`. `true` uses the default injection settings; pass a [MemoryInjectionConfig](/docs/api/typescript/MemoryInjectionConfig/index.md) to customize retrieval, timing, and formatting; `false` disables it.

`true` is equivalent to:

```ts
{
  trigger: 'userTurn',          // inject only on a fresh user ask
  maxEntries: 5,                // retrieve and inject up to 5 entries
  // query:  the latest user text on a user turn, else the most recent assistant text
  // format: a <memory> block with one <entry source="STORE_NAME"> per result (content escaped)
}
```