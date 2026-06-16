```ts
const InterventionActions: {
  proceed: (options?) => Proceed;
  deny: (reason) => Deny;
  guide: (feedback, options?) => Guide;
  confirm: (prompt, options?) => Confirm;
  transform: (apply, options?) => Transform;
};
```

Defined in: [src/interventions/index.ts:3](https://github.com/strands-agents/harness-sdk/blob/49d797ae86485bd24e3e86744b6b959ccc8b9a12/strands-ts/src/interventions/index.ts#L3)

## Type Declaration

| Name | Type | Defined in |
| --- | --- | --- |
| `proceed()` | (`options?`) => `Proceed` | [src/interventions/index.ts:3](https://github.com/strands-agents/harness-sdk/blob/49d797ae86485bd24e3e86744b6b959ccc8b9a12/strands-ts/src/interventions/index.ts#L3) |
| `deny()` | (`reason`) => `Deny` | [src/interventions/index.ts:3](https://github.com/strands-agents/harness-sdk/blob/49d797ae86485bd24e3e86744b6b959ccc8b9a12/strands-ts/src/interventions/index.ts#L3) |
| `guide()` | (`feedback`, `options?`) => `Guide` | [src/interventions/index.ts:3](https://github.com/strands-agents/harness-sdk/blob/49d797ae86485bd24e3e86744b6b959ccc8b9a12/strands-ts/src/interventions/index.ts#L3) |
| `confirm()` | (`prompt`, `options?`) => `Confirm` | [src/interventions/index.ts:3](https://github.com/strands-agents/harness-sdk/blob/49d797ae86485bd24e3e86744b6b959ccc8b9a12/strands-ts/src/interventions/index.ts#L3) |
| `transform()` | (`apply`, `options?`) => `Transform` | [src/interventions/index.ts:3](https://github.com/strands-agents/harness-sdk/blob/49d797ae86485bd24e3e86744b6b959ccc8b9a12/strands-ts/src/interventions/index.ts#L3) |