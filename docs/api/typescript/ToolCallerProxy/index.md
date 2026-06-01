```ts
type ToolCallerProxy = Record<string, ToolHandle>;
```

Defined in: [src/agent/tool-caller.ts:68](https://github.com/strands-agents/sdk-typescript/blob/e0658993e83c0a615dc91695915f48eda36ba169/strands-ts/src/agent/tool-caller.ts#L68)

The public type of the tool caller proxy. Provides dynamic property access where each property is a [ToolHandle](/docs/api/typescript/ToolHandle/index.md) with `.invoke()` and `.stream()` methods.