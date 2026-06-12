Defined in: [src/middleware/stages.ts:105](https://github.com/strands-agents/harness-sdk/blob/db79d737433905152b5d3dfe9f110fb00f4d2fa6/strands-ts/src/middleware/stages.ts#L105)

Context passed to tool-stage middleware. Contains everything needed to understand and potentially modify the tool call.

## Extends

-   [`MiddlewareInterruptible`](/docs/api/typescript/MiddlewareInterruptible/index.md)

## Properties

### agent

```ts
readonly agent: LocalAgent;
```

Defined in: [src/middleware/stages.ts:107](https://github.com/strands-agents/harness-sdk/blob/db79d737433905152b5d3dfe9f110fb00f4d2fa6/strands-ts/src/middleware/stages.ts#L107)

The agent instance (escape hatch for advanced use cases).

---

### tool

```ts
readonly tool: Tool;
```

Defined in: [src/middleware/stages.ts:109](https://github.com/strands-agents/harness-sdk/blob/db79d737433905152b5d3dfe9f110fb00f4d2fa6/strands-ts/src/middleware/stages.ts#L109)

The resolved tool implementation, or undefined if not found.

---

### toolUse

```ts
readonly toolUse: ToolUseData;
```

Defined in: [src/middleware/stages.ts:111](https://github.com/strands-agents/harness-sdk/blob/db79d737433905152b5d3dfe9f110fb00f4d2fa6/strands-ts/src/middleware/stages.ts#L111)

The tool use request (name, toolUseId, input).

---

### invocationState

```ts
readonly invocationState: InvocationState;
```

Defined in: [src/middleware/stages.ts:113](https://github.com/strands-agents/harness-sdk/blob/db79d737433905152b5d3dfe9f110fb00f4d2fa6/strands-ts/src/middleware/stages.ts#L113)

Per-invocation state shared across hooks and tools.

## Methods

### interrupt()

```ts
interrupt<T>(params): MiddlewareInterruptResult<T>;
```

Defined in: [src/middleware/stages.ts:51](https://github.com/strands-agents/harness-sdk/blob/db79d737433905152b5d3dfe9f110fb00f4d2fa6/strands-ts/src/middleware/stages.ts#L51)

Request a human-in-the-loop interrupt.

On first execution (no prior response), throws `InterruptError` to halt the agent. On resume (after the user provides a response), returns the response wrapped in `MiddlewareInterruptResult`.

#### Type Parameters

| Type Parameter | Default type |
| --- | --- |
| `T` | [`JSONValue`](/docs/api/typescript/JSONValue/index.md) |

#### Parameters

| Parameter | Type | Description |
| --- | --- | --- |
| `params` | [`InterruptParams`](/docs/api/typescript/InterruptParams/index.md) | Interrupt parameters (name, optional reason, optional preemptive response) |

#### Returns

[`MiddlewareInterruptResult`](/docs/api/typescript/MiddlewareInterruptResult/index.md)<`T`\>

The user’s response wrapped in `{ response: T }`

#### Throws

InterruptError when no response has been provided yet

#### Inherited from

[`MiddlewareInterruptible`](/docs/api/typescript/MiddlewareInterruptible/index.md).[`interrupt`](/docs/api/typescript/MiddlewareInterruptible/index.md#interrupt)