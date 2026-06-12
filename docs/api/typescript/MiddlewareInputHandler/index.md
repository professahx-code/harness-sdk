```ts
type MiddlewareInputHandler<TContext> = (context) => TContext | Promise<TContext>;
```

Defined in: [src/middleware/types.ts:75](https://github.com/strands-agents/harness-sdk/blob/db79d737433905152b5d3dfe9f110fb00f4d2fa6/strands-ts/src/middleware/types.ts#L75)

Handler for Input phase — transforms context before execution.

## Type Parameters

| Type Parameter |
| --- |
| `TContext` |

## Parameters

| Parameter | Type |
| --- | --- |
| `context` | `TContext` |

## Returns

`TContext` | `Promise`<`TContext`\>