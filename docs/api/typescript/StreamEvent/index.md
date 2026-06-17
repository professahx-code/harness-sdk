Defined in: [src/hooks/events.ts:81](https://github.com/strands-agents/harness-sdk/blob/d88911386ffd4b5f924c7b896ad24f288632baec/strands-ts/src/hooks/events.ts#L81)

Base class for all events yielded by `agent.stream()`. Carries no hookability — subclasses that should be hookable extend [HookableEvent](/docs/api/typescript/HookableEvent/index.md) instead.

## Extended by

-   [`HookableEvent`](/docs/api/typescript/HookableEvent/index.md)

## Constructors

### Constructor

```ts
new StreamEvent(): StreamEvent;
```

#### Returns

`StreamEvent`