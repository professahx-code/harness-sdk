Defined in: [src/middleware/stages.ts:75](https://github.com/strands-agents/harness-sdk/blob/db79d737433905152b5d3dfe9f110fb00f4d2fa6/strands-ts/src/middleware/stages.ts#L75)

Context passed to model-stage middleware. All inputs to the model call are explicit — middleware can inspect and transform any of them by passing a modified context to next().

## Properties

### agent

```ts
readonly agent: LocalAgent;
```

Defined in: [src/middleware/stages.ts:77](https://github.com/strands-agents/harness-sdk/blob/db79d737433905152b5d3dfe9f110fb00f4d2fa6/strands-ts/src/middleware/stages.ts#L77)

The agent instance (escape hatch for advanced use cases).

---

### messages

```ts
readonly messages: readonly Message[];
```

Defined in: [src/middleware/stages.ts:79](https://github.com/strands-agents/harness-sdk/blob/db79d737433905152b5d3dfe9f110fb00f4d2fa6/strands-ts/src/middleware/stages.ts#L79)

The messages to send to the model.

---

### systemPrompt?

```ts
readonly optional systemPrompt?: SystemPrompt;
```

Defined in: [src/middleware/stages.ts:81](https://github.com/strands-agents/harness-sdk/blob/db79d737433905152b5d3dfe9f110fb00f4d2fa6/strands-ts/src/middleware/stages.ts#L81)

System prompt to guide the model’s behavior.

---

### toolSpecs

```ts
readonly toolSpecs: readonly ToolSpec[];
```

Defined in: [src/middleware/stages.ts:83](https://github.com/strands-agents/harness-sdk/blob/db79d737433905152b5d3dfe9f110fb00f4d2fa6/strands-ts/src/middleware/stages.ts#L83)

Tool specifications available to the model.

---

### toolChoice?

```ts
readonly optional toolChoice?: ToolChoice;
```

Defined in: [src/middleware/stages.ts:85](https://github.com/strands-agents/harness-sdk/blob/db79d737433905152b5d3dfe9f110fb00f4d2fa6/strands-ts/src/middleware/stages.ts#L85)

Controls how the model selects tools.

---

### modelState

```ts
readonly modelState: StateStore;
```

Defined in: [src/middleware/stages.ts:87](https://github.com/strands-agents/harness-sdk/blob/db79d737433905152b5d3dfe9f110fb00f4d2fa6/strands-ts/src/middleware/stages.ts#L87)

Runtime state for stateful model providers.

---

### invocationState

```ts
readonly invocationState: InvocationState;
```

Defined in: [src/middleware/stages.ts:89](https://github.com/strands-agents/harness-sdk/blob/db79d737433905152b5d3dfe9f110fb00f4d2fa6/strands-ts/src/middleware/stages.ts#L89)

Per-invocation state shared across hooks and tools.