Defined in: [src/sandbox/errors.ts:32](https://github.com/strands-agents/harness-sdk/blob/d88911386ffd4b5f924c7b896ad24f288632baec/strands-ts/src/sandbox/errors.ts#L32)

Thrown by [Sandbox.listFiles](/docs/api/typescript/Sandbox/index.md#listfiles) when the path does not exist, distinguishing genuine absence from permission or transport failures (which throw plain errors).

## Extends

-   `Error`

## Constructors

### Constructor

```ts
new SandboxPathNotFoundError(path): SandboxPathNotFoundError;
```

Defined in: [src/sandbox/errors.ts:33](https://github.com/strands-agents/harness-sdk/blob/d88911386ffd4b5f924c7b896ad24f288632baec/strands-ts/src/sandbox/errors.ts#L33)

#### Parameters

| Parameter | Type |
| --- | --- |
| `path` | `string` |

#### Returns

`SandboxPathNotFoundError`

#### Overrides

```ts
Error.constructor
```