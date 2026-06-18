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

Defined in: [src/types/media.ts:389](https://github.com/strands-agents/harness-sdk/blob/d77b68e333e3afa20815a6cd85c867acc8273d92/strands-ts/src/types/media.ts#L389)

Source for a document (Class version).