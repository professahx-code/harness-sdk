```ts
type VideoSourceData =
  | {
  bytes: Uint8Array;
}
  | {
  location: S3LocationData;
};
```

Defined in: [src/types/media.ts:265](https://github.com/strands-agents/harness-sdk/blob/1e560f5e65f4a9458aaf61c65b02c8cb1fe21345/strands-ts/src/types/media.ts#L265)

Source for a video (Data version).