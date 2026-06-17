```ts
type RetryDecision =
  | {
  retry: false;
}
  | {
  retry: true;
  waitMs: number;
};
```

Defined in: [src/retry/retry-strategy.ts:25](https://github.com/strands-agents/harness-sdk/blob/1e560f5e65f4a9458aaf61c65b02c8cb1fe21345/strands-ts/src/retry/retry-strategy.ts#L25)

Decision returned by a retry strategy’s per-event `compute*RetryDecision` method.

Discriminated union: `retry: true` carries the wait duration the framework will sleep for before re-invoking the failed operation. `retry: false` carries nothing — the error propagates to the caller.

Shared across retry kinds (model retries today; tool retries and others later) so all strategies speak the same decision shape.