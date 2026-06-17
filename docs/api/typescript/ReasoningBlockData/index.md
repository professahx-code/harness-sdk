Defined in: [src/types/messages.ts:444](https://github.com/strands-agents/harness-sdk/blob/1e560f5e65f4a9458aaf61c65b02c8cb1fe21345/strands-ts/src/types/messages.ts#L444)

Data for a reasoning block.

## Properties

### text?

```ts
optional text?: string;
```

Defined in: [src/types/messages.ts:448](https://github.com/strands-agents/harness-sdk/blob/1e560f5e65f4a9458aaf61c65b02c8cb1fe21345/strands-ts/src/types/messages.ts#L448)

The text content of the reasoning process.

---

### signature?

```ts
optional signature?: string;
```

Defined in: [src/types/messages.ts:453](https://github.com/strands-agents/harness-sdk/blob/1e560f5e65f4a9458aaf61c65b02c8cb1fe21345/strands-ts/src/types/messages.ts#L453)

A cryptographic signature for verification purposes.

---

### redactedContent?

```ts
optional redactedContent?: Uint8Array;
```

Defined in: [src/types/messages.ts:458](https://github.com/strands-agents/harness-sdk/blob/1e560f5e65f4a9458aaf61c65b02c8cb1fe21345/strands-ts/src/types/messages.ts#L458)

The redacted content of the reasoning process.