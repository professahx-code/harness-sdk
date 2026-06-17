Defined in: [src/memory/extraction/types.ts:82](https://github.com/strands-agents/harness-sdk/blob/278805cd559e63475a4c6f52f52614fffa99e401/strands-ts/src/memory/extraction/types.ts#L82)

Context handed to [ExtractionTrigger.attach](/docs/api/typescript/ExtractionTrigger/index.md#attach) so a trigger can wire itself into the agent lifecycle and signal when extraction should run for its store.

## Properties

### agent

```ts
agent: LocalAgent;
```

Defined in: [src/memory/extraction/types.ts:84](https://github.com/strands-agents/harness-sdk/blob/278805cd559e63475a4c6f52f52614fffa99e401/strands-ts/src/memory/extraction/types.ts#L84)

The agent the trigger attaches its hooks to.

---

### fire

```ts
fire: () => void;
```

Defined in: [src/memory/extraction/types.ts:86](https://github.com/strands-agents/harness-sdk/blob/278805cd559e63475a4c6f52f52614fffa99e401/strands-ts/src/memory/extraction/types.ts#L86)

Save this store’s unsaved messages now. Runs in the background and returns immediately, so calling it from a hook never blocks the agent. To await completion, see [MemoryManager.flush](/docs/api/typescript/MemoryManager/index.md#flush).

#### Returns

`void`