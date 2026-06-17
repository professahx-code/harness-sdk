```ts
type DocumentSource =
  | {
  type: "documentSourceBytes";
  bytes: Uint8Array;
}
  | {
  type: "documentSourceText";
  text: string;
}
  | {
  type: "documentSourceContentBlock";
  content: DocumentContentBlock[];
}
  | {
  type: "documentSourceS3Location";
  location: S3Location;
};
```

Defined in: [src/types/media.ts:389](https://github.com/strands-agents/harness-sdk/blob/278805cd559e63475a4c6f52f52614fffa99e401/strands-ts/src/types/media.ts#L389)

Source for a document (Class version).