Defined in: [src/memory/extraction/types.ts:27](https://github.com/strands-agents/harness-sdk/blob/d77b68e333e3afa20815a6cd85c867acc8273d92/strands-ts/src/memory/extraction/types.ts#L27)

Filters content blocks out of messages before extraction.

Blocks whose kind is in [exclude](#exclude) are stripped; a message left with no content is dropped entirely. Defaults to excluding tool traffic (`toolUse` / `toolResult`), which is rarely useful as long-term memory and adds noise.

## Properties

### exclude

```ts
exclude: MemoryContentBlockType[];
```

Defined in: [src/memory/extraction/types.ts:29](https://github.com/strands-agents/harness-sdk/blob/d77b68e333e3afa20815a6cd85c867acc8273d92/strands-ts/src/memory/extraction/types.ts#L29)

Content block kinds to strip before extraction.