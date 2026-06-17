```ts
type SessionStorage = {
  snapshot: SnapshotStorage;
};
```

Defined in: [src/session/storage.ts:26](https://github.com/strands-agents/harness-sdk/blob/278805cd559e63475a4c6f52f52614fffa99e401/strands-ts/src/session/storage.ts#L26)

SessionStorage configuration for pluggable storage backends. Allows users to configure snapshot and transcript storage independently.

## Example

```typescript
const storage: SessionStorage = {
  snapshot: new S3Storage({ bucket: 'my-bucket' })
}
```

## Properties

### snapshot

```ts
snapshot: SnapshotStorage;
```

Defined in: [src/session/storage.ts:27](https://github.com/strands-agents/harness-sdk/blob/278805cd559e63475a4c6f52f52614fffa99e401/strands-ts/src/session/storage.ts#L27)