```ts
type HookCallback<T> = (event) => void | Promise<void>;
```

Defined in: [src/hooks/types.ts:20](https://github.com/strands-agents/harness-sdk/blob/db79d737433905152b5d3dfe9f110fb00f4d2fa6/strands-ts/src/hooks/types.ts#L20)

Type for callback functions that handle hookable events. Callbacks can be synchronous or asynchronous.

## Type Parameters

| Type Parameter |
| --- |
| `T` *extends* [`HookableEvent`](/docs/api/typescript/HookableEvent/index.md) |

## Parameters

| Parameter | Type |
| --- | --- |
| `event` | `T` |

## Returns

`void` | `Promise`<`void`\>

## Example

```typescript
const callback: HookCallback<BeforeInvocationEvent> = (event) => {
  console.log('Agent invocation started')
}
```