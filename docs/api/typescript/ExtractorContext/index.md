Defined in: [src/memory/extraction/types.ts:54](https://github.com/strands-agents/harness-sdk/blob/ba40a091b194165d20cd9270125d792cc647c2dd/strands-ts/src/memory/extraction/types.ts#L54)

Context passed to [Extractor.extract](/docs/api/typescript/Extractor/index.md#extract).

Lets the manager hand an extractor a fallback model without the extractor having to be wired to the agent directly. [ModelExtractor](/docs/api/typescript/ModelExtractor/index.md) uses its own configured model when set, else [defaultModel](#defaultmodel).

## Properties

### defaultModel?

```ts
optional defaultModel?: Model;
```

Defined in: [src/memory/extraction/types.ts:56](https://github.com/strands-agents/harness-sdk/blob/ba40a091b194165d20cd9270125d792cc647c2dd/strands-ts/src/memory/extraction/types.ts#L56)

The agent’s model, supplied so an extractor can default to it.