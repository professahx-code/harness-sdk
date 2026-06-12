Defined in: [src/memory/types.ts:42](https://github.com/strands-agents/harness-sdk/blob/db79d737433905152b5d3dfe9f110fb00f4d2fa6/strands-ts/src/memory/types.ts#L42)

Context the [MemoryManager](/docs/api/typescript/MemoryManager/index.md) supplies to [MemoryStore.addMessages](/docs/api/typescript/MemoryStore/index.md#addmessages) alongside a batch.

An extension point: fields are added here without changing the [MemoryStore.addMessages](/docs/api/typescript/MemoryStore/index.md#addmessages) signature.

## Properties

### sequenceNumbers?

```ts
readonly optional sequenceNumbers?: readonly number[];
```

Defined in: [src/memory/types.ts:50](https://github.com/strands-agents/harness-sdk/blob/db79d737433905152b5d3dfe9f110fb00f4d2fa6/strands-ts/src/memory/types.ts#L50)

Per-message identities aligned one-to-one with `messages` (`sequenceNumbers[i]` identifies `messages[i]`). A retried batch reuses the same numbers, so a store can build an idempotency key that survives retries - unlike a content hash, which collides when two messages share text (e.g. “ok”). Numbers increase with order but may have gaps, and reset to 0 each agent run, so a durable dedup token must combine one with a run-unique id.