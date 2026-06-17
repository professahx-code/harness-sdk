```ts
type MiddlewareNext<TContext, TResult, TEvent> = (context) => AsyncGenerator<TEvent, TResult, undefined>;
```

Defined in: [src/middleware/types.ts:59](https://github.com/strands-agents/harness-sdk/blob/1e560f5e65f4a9458aaf61c65b02c8cb1fe21345/strands-ts/src/middleware/types.ts#L59)

The `next` function passed to middleware. Returns an async generator that yields events of type TEvent and returns the stage result. Middleware can choose not to call `next` to short-circuit execution.

## Type Parameters

| Type Parameter |
| --- |
| `TContext` |
| `TResult` |
| `TEvent` |

## Parameters

| Parameter | Type |
| --- | --- |
| `context` | `TContext` |

## Returns

`AsyncGenerator`<`TEvent`, `TResult`, `undefined`\>