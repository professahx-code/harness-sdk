```ts
type VideoSource =
  | {
  type: "videoSourceBytes";
  bytes: Uint8Array;
}
  | {
  type: "videoSourceS3Location";
  location: S3Location;
};
```

Defined in: [src/types/media.ts:270](https://github.com/strands-agents/harness-sdk/blob/d88911386ffd4b5f924c7b896ad24f288632baec/strands-ts/src/types/media.ts#L270)

Source for a video (Class version).