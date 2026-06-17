```ts
type ToolStreamGenerator = AsyncGenerator<ToolStreamEvent, ToolResultBlock, undefined>;
```

Defined in: [src/tools/tool.ts:93](https://github.com/strands-agents/harness-sdk/blob/d88911386ffd4b5f924c7b896ad24f288632baec/strands-ts/src/tools/tool.ts#L93)

Type alias for the async generator returned by tool stream methods. Yields ToolStreamEvents during execution and returns a ToolResultBlock.