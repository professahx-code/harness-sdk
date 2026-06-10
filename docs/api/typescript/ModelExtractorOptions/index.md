Defined in: [src/memory/extraction/model-extractor.ts:13](https://github.com/strands-agents/harness-sdk/blob/3db1b6375bb18b5c12c42650c6fea93014b9c687/strands-ts/src/memory/extraction/model-extractor.ts#L13)

Options for [ModelExtractor](/docs/api/typescript/ModelExtractor/index.md).

## Properties

### model?

```ts
optional model?: Model;
```

Defined in: [src/memory/extraction/model-extractor.ts:15](https://github.com/strands-agents/harness-sdk/blob/3db1b6375bb18b5c12c42650c6fea93014b9c687/strands-ts/src/memory/extraction/model-extractor.ts#L15)

Model used to extract facts. Defaults to the agent’s own model; set a cheaper one to cut cost.

---

### systemPrompt?

```ts
optional systemPrompt?: string;
```

Defined in: [src/memory/extraction/model-extractor.ts:17](https://github.com/strands-agents/harness-sdk/blob/3db1b6375bb18b5c12c42650c6fea93014b9c687/strands-ts/src/memory/extraction/model-extractor.ts#L17)

System prompt steering what counts as a fact. Defaults to a general fact-extraction prompt.