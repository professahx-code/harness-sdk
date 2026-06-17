```ts
function configureLogging(customLogger): void;
```

Defined in: [src/logging/logger.ts:44](https://github.com/strands-agents/harness-sdk/blob/7ac039e427e4b488f61a6af1c827532f46dfffa1/strands-ts/src/logging/logger.ts#L44)

Configures the global logger.

Allows users to inject their own logger implementation (e.g., Pino, Winston) to control logging behavior, levels, and formatting.

## Parameters

| Parameter | Type | Description |
| --- | --- | --- |
| `customLogger` | [`Logger`](/docs/api/typescript/Logger/index.md) | The logger implementation to use |

## Returns

`void`

## Example

```typescript
import pino from 'pino'
import { configureLogging } from '@strands-agents/sdk'

const logger = pino({ level: 'debug' })
configureLogging(logger)
```