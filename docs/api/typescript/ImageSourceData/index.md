```ts
type ImageSourceData =
  | {
  bytes: Uint8Array;
}
  | {
  location: S3LocationData;
}
  | {
  url: string;
};
```

Defined in: [src/types/media.ts:141](https://github.com/strands-agents/harness-sdk/blob/ba40a091b194165d20cd9270125d792cc647c2dd/strands-ts/src/types/media.ts#L141)

Source for an image (Data version). Supports multiple formats for different providers.