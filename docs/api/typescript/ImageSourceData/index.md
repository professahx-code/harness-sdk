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

Defined in: [src/types/media.ts:141](https://github.com/strands-agents/harness-sdk/blob/49d797ae86485bd24e3e86744b6b959ccc8b9a12/strands-ts/src/types/media.ts#L141)

Source for an image (Data version). Supports multiple formats for different providers.