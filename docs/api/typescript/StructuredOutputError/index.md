Defined in: [src/errors.ts:203](https://github.com/strands-agents/harness-sdk/blob/d88911386ffd4b5f924c7b896ad24f288632baec/strands-ts/src/errors.ts#L203)

Thrown when the model fails to produce structured output. This occurs when the LLM refuses to use the structured output tool even after being forced via toolChoice.

## Extends

-   `Error`

## Constructors

### Constructor

```ts
new StructuredOutputError(message): StructuredOutputError;
```

Defined in: [src/errors.ts:204](https://github.com/strands-agents/harness-sdk/blob/d88911386ffd4b5f924c7b896ad24f288632baec/strands-ts/src/errors.ts#L204)

#### Parameters

| Parameter | Type |
| --- | --- |
| `message` | `string` |

#### Returns

`StructuredOutputError`

#### Overrides

```ts
Error.constructor
```