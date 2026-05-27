```ts
const InterventionActions: {
  proceed: (options?) => Proceed;
  deny: (reason) => Deny;
  guide: (feedback, options?) => Guide;
  confirm: (prompt, options?) => Confirm;
  transform: (apply, options?) => Transform;
};
```

Defined in: [src/interventions/index.ts:3](https://github.com/strands-agents/sdk-typescript/blob/0f99011408c45dcc6ca403794f60c05a1ac61eb8/strands-ts/src/interventions/index.ts#L3)

## Type Declaration

| Name | Type | Defined in |
| --- | --- | --- |
| `proceed()` | (`options?`) => `Proceed` | [src/interventions/index.ts:3](https://github.com/strands-agents/sdk-typescript/blob/0f99011408c45dcc6ca403794f60c05a1ac61eb8/strands-ts/src/interventions/index.ts#L3) |
| `deny()` | (`reason`) => `Deny` | [src/interventions/index.ts:3](https://github.com/strands-agents/sdk-typescript/blob/0f99011408c45dcc6ca403794f60c05a1ac61eb8/strands-ts/src/interventions/index.ts#L3) |
| `guide()` | (`feedback`, `options?`) => `Guide` | [src/interventions/index.ts:3](https://github.com/strands-agents/sdk-typescript/blob/0f99011408c45dcc6ca403794f60c05a1ac61eb8/strands-ts/src/interventions/index.ts#L3) |
| `confirm()` | (`prompt`, `options?`) => `Confirm` | [src/interventions/index.ts:3](https://github.com/strands-agents/sdk-typescript/blob/0f99011408c45dcc6ca403794f60c05a1ac61eb8/strands-ts/src/interventions/index.ts#L3) |
| `transform()` | (`apply`, `options?`) => `Transform` | [src/interventions/index.ts:3](https://github.com/strands-agents/sdk-typescript/blob/0f99011408c45dcc6ca403794f60c05a1ac61eb8/strands-ts/src/interventions/index.ts#L3) |