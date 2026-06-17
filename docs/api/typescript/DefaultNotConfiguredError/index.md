Defined in: [src/errors.ts:251](https://github.com/strands-agents/harness-sdk/blob/c04fdd821ea0e816a78fdf2e3f95201e3cfa84c5/strands-ts/src/errors.ts#L251)

Thrown when a default value is read before one has been configured.

Catch it to distinguish a missing-default condition from other runtime errors.

## Extends

-   `Error`

## Constructors

### Constructor

```ts
new DefaultNotConfiguredError(message): DefaultNotConfiguredError;
```

Defined in: [src/errors.ts:252](https://github.com/strands-agents/harness-sdk/blob/c04fdd821ea0e816a78fdf2e3f95201e3cfa84c5/strands-ts/src/errors.ts#L252)

#### Parameters

| Parameter | Type |
| --- | --- |
| `message` | `string` |

#### Returns

`DefaultNotConfiguredError`

#### Overrides

```ts
Error.constructor
```