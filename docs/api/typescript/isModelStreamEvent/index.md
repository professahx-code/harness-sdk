```ts
function isModelStreamEvent(event): event is ModelStreamEvent;
```

Defined in: [src/models/streaming.ts:44](https://github.com/strands-agents/harness-sdk/blob/49d797ae86485bd24e3e86744b6b959ccc8b9a12/strands-ts/src/models/streaming.ts#L44)

Type guard to check if an event with a type discriminator is a ModelStreamEvent.

## Parameters

| Parameter | Type | Description |
| --- | --- | --- |
| `event` | { `type`: `string`; } | The event to check |
| `event.type` | `string` | \- |

## Returns

`event is ModelStreamEvent`

true if the event is a ModelStreamEvent