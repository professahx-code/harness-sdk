Defined in: [src/middleware/stages.ts:129](https://github.com/strands-agents/harness-sdk/blob/db79d737433905152b5d3dfe9f110fb00f4d2fa6/strands-ts/src/middleware/stages.ts#L129)

Context passed to agent-stream-stage middleware. Wraps the entire agent output stream at the outermost interception point.

## Extends

-   [`MiddlewareInterruptible`](/docs/api/typescript/MiddlewareInterruptible/index.md)

## Properties

### agent

```ts
readonly agent: LocalAgent;
```

Defined in: [src/middleware/stages.ts:131](https://github.com/strands-agents/harness-sdk/blob/db79d737433905152b5d3dfe9f110fb00f4d2fa6/strands-ts/src/middleware/stages.ts#L131)

The agent instance (escape hatch for advanced use cases).

---

### args

```ts
readonly args: InvokeArgs;
```

Defined in: [src/middleware/stages.ts:133](https://github.com/strands-agents/harness-sdk/blob/db79d737433905152b5d3dfe9f110fb00f4d2fa6/strands-ts/src/middleware/stages.ts#L133)

The invocation arguments passed to agent.stream().

---

### options?

```ts
readonly optional options?: InvokeOptions;
```

Defined in: [src/middleware/stages.ts:135](https://github.com/strands-agents/harness-sdk/blob/db79d737433905152b5d3dfe9f110fb00f4d2fa6/strands-ts/src/middleware/stages.ts#L135)

Per-invocation options (cancel signal, structured output, etc.).

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