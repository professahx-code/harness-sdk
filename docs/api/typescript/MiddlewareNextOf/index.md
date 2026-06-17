```ts
type MiddlewareNextOf<S> = S extends MiddlewareStage<infer C, infer R, infer E> ? MiddlewareNext<C, R, E> : never;
```

Defined in: [src/middleware/types.ts:103](https://github.com/strands-agents/harness-sdk/blob/1e560f5e65f4a9458aaf61c65b02c8cb1fe21345/strands-ts/src/middleware/types.ts#L103)

Extracts the `MiddlewareNext` type from a stage token. Use this to type the `next` parameter in standalone middleware methods.

## Type Parameters

| Type Parameter |
| --- |
| `S` |

## Example

```typescript
private async *_handler(context: ..., next: MiddlewareNextOf<typeof AgentStreamStage>) { ... }
```