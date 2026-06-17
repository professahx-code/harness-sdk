Defined in: [src/types/messages.ts:222](https://github.com/strands-agents/harness-sdk/blob/d88911386ffd4b5f924c7b896ad24f288632baec/strands-ts/src/types/messages.ts#L222)

Data for a tool use block.

## Properties

### name

```ts
name: string;
```

Defined in: [src/types/messages.ts:226](https://github.com/strands-agents/harness-sdk/blob/d88911386ffd4b5f924c7b896ad24f288632baec/strands-ts/src/types/messages.ts#L226)

The name of the tool to execute.

---

### toolUseId

```ts
toolUseId: string;
```

Defined in: [src/types/messages.ts:231](https://github.com/strands-agents/harness-sdk/blob/d88911386ffd4b5f924c7b896ad24f288632baec/strands-ts/src/types/messages.ts#L231)

Unique identifier for this tool use instance.

---

### input

```ts
input: JSONValue;
```

Defined in: [src/types/messages.ts:237](https://github.com/strands-agents/harness-sdk/blob/d88911386ffd4b5f924c7b896ad24f288632baec/strands-ts/src/types/messages.ts#L237)

The input parameters for the tool. This can be any JSON-serializable value.

---

### reasoningSignature?

```ts
optional reasoningSignature?: string;
```

Defined in: [src/types/messages.ts:243](https://github.com/strands-agents/harness-sdk/blob/d88911386ffd4b5f924c7b896ad24f288632baec/strands-ts/src/types/messages.ts#L243)

Reasoning signature from thinking models (e.g., Gemini). Must be preserved and sent back to the model for multi-turn tool use.