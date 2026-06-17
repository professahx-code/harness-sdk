Defined in: [src/sandbox/errors.ts:11](https://github.com/strands-agents/harness-sdk/blob/ba40a091b194165d20cd9270125d792cc647c2dd/strands-ts/src/sandbox/errors.ts#L11)

Thrown by sandbox execution when the configured `timeout` elapses.

## Extends

-   `Error`

## Constructors

### Constructor

```ts
new SandboxTimeoutError(seconds): SandboxTimeoutError;
```

Defined in: [src/sandbox/errors.ts:12](https://github.com/strands-agents/harness-sdk/blob/ba40a091b194165d20cd9270125d792cc647c2dd/strands-ts/src/sandbox/errors.ts#L12)

#### Parameters

| Parameter | Type |
| --- | --- |
| `seconds` | `number` |

#### Returns

`SandboxTimeoutError`

#### Overrides

```ts
Error.constructor
```