Defined in: [src/memory/extraction/model-extractor.ts:13](https://github.com/strands-agents/harness-sdk/blob/ba40a091b194165d20cd9270125d792cc647c2dd/strands-ts/src/memory/extraction/model-extractor.ts#L13)

Options for [ModelExtractor](/docs/api/typescript/ModelExtractor/index.md).

## Properties

### model?

```ts
optional model?: Model;
```

Defined in: [src/memory/extraction/model-extractor.ts:15](https://github.com/strands-agents/harness-sdk/blob/ba40a091b194165d20cd9270125d792cc647c2dd/strands-ts/src/memory/extraction/model-extractor.ts#L15)

Model used to extract facts. Defaults to the agent’s own model; set a cheaper one to cut cost.

---

### systemPrompt?

```ts
optional systemPrompt?: string;
```

Defined in: [src/memory/extraction/model-extractor.ts:17](https://github.com/strands-agents/harness-sdk/blob/ba40a091b194165d20cd9270125d792cc647c2dd/strands-ts/src/memory/extraction/model-extractor.ts#L17)

System prompt steering what counts as a fact. Defaults to a general fact-extraction prompt.