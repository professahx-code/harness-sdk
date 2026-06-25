Defined in: [src/types/messages.ts:839](https://github.com/strands-agents/harness-sdk/blob/d9b9061486aa20414699f47b5b1caddccb3e0dff/strands-ts/src/types/messages.ts#L839)

Data for a guard content block. Can contain either text or image content for guardrail evaluation.

## Properties

### text?

```ts
optional text?: GuardContentText;
```

Defined in: [src/types/messages.ts:843](https://github.com/strands-agents/harness-sdk/blob/d9b9061486aa20414699f47b5b1caddccb3e0dff/strands-ts/src/types/messages.ts#L843)

Text content with evaluation qualifiers.

---

### image?

```ts
optional image?: GuardContentImage;
```

Defined in: [src/types/messages.ts:848](https://github.com/strands-agents/harness-sdk/blob/d9b9061486aa20414699f47b5b1caddccb3e0dff/strands-ts/src/types/messages.ts#L848)

Image content with evaluation qualifiers.