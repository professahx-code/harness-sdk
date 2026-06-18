```ts
type ToolCallerProxy = Record<string, ToolHandle>;
```

Defined in: [src/agent/tool-caller.ts:68](https://github.com/strands-agents/harness-sdk/blob/ef0ed3b3df5c6383d9c6082895aa87e52b2adc1a/strands-ts/src/agent/tool-caller.ts#L68)

The public type of the tool caller proxy. Provides dynamic property access where each property is a [ToolHandle](/docs/api/typescript/ToolHandle/index.md) with `.invoke()` and `.stream()` methods.