Defined in: [src/tools/tool.ts:41](https://github.com/strands-agents/harness-sdk/blob/7ac039e427e4b488f61a6af1c827532f46dfffa1/strands-ts/src/tools/tool.ts#L41)

Data for a tool stream event.

## Properties

### type

```ts
type: "toolStreamEvent";
```

Defined in: [src/tools/tool.ts:45](https://github.com/strands-agents/harness-sdk/blob/7ac039e427e4b488f61a6af1c827532f46dfffa1/strands-ts/src/tools/tool.ts#L45)

Discriminator for tool stream events.

---

### data?

```ts
optional data?: unknown;
```

Defined in: [src/tools/tool.ts:51](https://github.com/strands-agents/harness-sdk/blob/7ac039e427e4b488f61a6af1c827532f46dfffa1/strands-ts/src/tools/tool.ts#L51)

Caller-provided data for the progress update. Can be any type of data the tool wants to report.