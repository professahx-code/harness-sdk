Defined in: [src/sandbox/posix-shell.ts:78](https://github.com/strands-agents/harness-sdk/blob/3db1b6375bb18b5c12c42650c6fea93014b9c687/strands-ts/src/sandbox/posix-shell.ts#L78)

Abstract sandbox that provides shell-based defaults for file and code operations. Assumes a POSIX-compatible shell (sh/bash) on the target.

Subclasses only need to implement [executeStreaming](#executestreaming). The remaining operations — `executeCodeStreaming`, `readFile`, `writeFile`, `removeFile`, and `listFiles` — are implemented via shell commands piped through `executeStreaming`.

Subclasses may override any method with a native implementation for better performance or to handle edge cases (e.g., binary-safe file transfer via Docker stdin pipes, or native API calls for cloud backends).

Subclasses must apply `options.env` in `executeStreaming` or it has no effect: backends that build a shell-command string prepend buildShellEnvPrefix; backends that set env via process flags (e.g. Docker’s `-e`) call validateEnvKeys and pass the values directly.

## Extends

-   [`Sandbox`](/docs/api/typescript/Sandbox/index.md)

## Constructors

### Constructor

```ts
new PosixShellSandbox(): PosixShellSandbox;
```

#### Returns

`PosixShellSandbox`

#### Inherited from

[`Sandbox`](/docs/api/typescript/Sandbox/index.md).[`constructor`](/docs/api/typescript/Sandbox/index.md#constructor)

## Methods

### executeStreaming()

```ts
abstract executeStreaming(command, options?): AsyncIterable<
  | StreamChunk
| ExecutionResult>;
```

Defined in: [src/sandbox/base.ts:53](https://github.com/strands-agents/harness-sdk/blob/3db1b6375bb18b5c12c42650c6fea93014b9c687/strands-ts/src/sandbox/base.ts#L53)

Execute a shell command, streaming output.

Yields [StreamChunk](/docs/api/typescript/StreamChunk/index.md) objects for stdout and stderr as output arrives. The final yield is an [ExecutionResult](/docs/api/typescript/ExecutionResult/index.md) with the exit code and complete output.

#### Parameters

| Parameter | Type | Description |
| --- | --- | --- |
| `command` | `string` | The shell command to execute. |
| `options?` | [`ExecuteOptions`](/docs/api/typescript/ExecuteOptions/index.md) | Execution options. |

#### Returns

`AsyncIterable`< | [`StreamChunk`](/docs/api/typescript/StreamChunk/index.md) | [`ExecutionResult`](/docs/api/typescript/ExecutionResult/index.md)\>

Async iterable yielding StreamChunks followed by a final ExecutionResult.

#### Inherited from

[`Sandbox`](/docs/api/typescript/Sandbox/index.md).[`executeStreaming`](/docs/api/typescript/Sandbox/index.md#executestreaming)

---

### execute()

```ts
execute(command, options?): Promise<ExecutionResult>;
```

Defined in: [src/sandbox/base.ts:125](https://github.com/strands-agents/harness-sdk/blob/3db1b6375bb18b5c12c42650c6fea93014b9c687/strands-ts/src/sandbox/base.ts#L125)

Execute a shell command and return the result.

Consumes [executeStreaming](/docs/api/typescript/Sandbox/index.md#executestreaming) and returns the final [ExecutionResult](/docs/api/typescript/ExecutionResult/index.md). Use `executeStreaming` when you need to process output as it arrives.

#### Parameters

| Parameter | Type | Description |
| --- | --- | --- |
| `command` | `string` | The shell command to execute. |
| `options?` | [`ExecuteOptions`](/docs/api/typescript/ExecuteOptions/index.md) | Execution options. |

#### Returns

`Promise`<[`ExecutionResult`](/docs/api/typescript/ExecutionResult/index.md)\>

The execution result with exit code and output.

#### Inherited from

[`Sandbox`](/docs/api/typescript/Sandbox/index.md).[`execute`](/docs/api/typescript/Sandbox/index.md#execute)

---

### executeCode()

```ts
executeCode(
   code,
   language,
options?): Promise<ExecutionResult>;
```

Defined in: [src/sandbox/base.ts:145](https://github.com/strands-agents/harness-sdk/blob/3db1b6375bb18b5c12c42650c6fea93014b9c687/strands-ts/src/sandbox/base.ts#L145)

Execute source code and return the result.

Consumes [executeCodeStreaming](/docs/api/typescript/Sandbox/index.md#executecodestreaming) and returns the final [ExecutionResult](/docs/api/typescript/ExecutionResult/index.md). Use `executeCodeStreaming` when you need to process output as it arrives.

#### Parameters

| Parameter | Type | Description |
| --- | --- | --- |
| `code` | `string` | The source code to execute. |
| `language` | `string` | The interpreter to use. |
| `options?` | [`ExecuteOptions`](/docs/api/typescript/ExecuteOptions/index.md) | Execution options. |

#### Returns

`Promise`<[`ExecutionResult`](/docs/api/typescript/ExecutionResult/index.md)\>

The execution result with exit code and output.

#### Inherited from

[`Sandbox`](/docs/api/typescript/Sandbox/index.md).[`executeCode`](/docs/api/typescript/Sandbox/index.md#executecode)

---

### readText()

```ts
readText(path): Promise<string>;
```

Defined in: [src/sandbox/base.ts:163](https://github.com/strands-agents/harness-sdk/blob/3db1b6375bb18b5c12c42650c6fea93014b9c687/strands-ts/src/sandbox/base.ts#L163)

Read a text file from the sandbox filesystem.

Convenience wrapper over [readFile](/docs/api/typescript/Sandbox/index.md#readfile) that decodes bytes as UTF-8. For other encodings, call `readFile` and decode manually.

#### Parameters

| Parameter | Type | Description |
| --- | --- | --- |
| `path` | `string` | Path to the file to read. |

#### Returns

`Promise`<`string`\>

The file contents decoded as a UTF-8 string.

#### Inherited from

[`Sandbox`](/docs/api/typescript/Sandbox/index.md).[`readText`](/docs/api/typescript/Sandbox/index.md#readtext)

---

### writeText()

```ts
writeText(path, content): Promise<void>;
```

Defined in: [src/sandbox/base.ts:176](https://github.com/strands-agents/harness-sdk/blob/3db1b6375bb18b5c12c42650c6fea93014b9c687/strands-ts/src/sandbox/base.ts#L176)

Write a text file to the sandbox filesystem.

Convenience wrapper over [writeFile](/docs/api/typescript/Sandbox/index.md#writefile) that encodes a string as UTF-8. For other encodings, encode manually and call `writeFile`.

#### Parameters

| Parameter | Type | Description |
| --- | --- | --- |
| `path` | `string` | Path to the file to write. |
| `content` | `string` | The text content to write. |

#### Returns

`Promise`<`void`\>

#### Inherited from

[`Sandbox`](/docs/api/typescript/Sandbox/index.md).[`writeText`](/docs/api/typescript/Sandbox/index.md#writetext)

---

### executeCodeStreaming()

```ts
executeCodeStreaming(
   code,
   language,
   options?): AsyncGenerator<
  | StreamChunk
| ExecutionResult, void, undefined>;
```

Defined in: [src/sandbox/posix-shell.ts:79](https://github.com/strands-agents/harness-sdk/blob/3db1b6375bb18b5c12c42650c6fea93014b9c687/strands-ts/src/sandbox/posix-shell.ts#L79)

Execute source code via a language interpreter, streaming output.

#### Parameters

| Parameter | Type | Description |
| --- | --- | --- |
| `code` | `string` | The source code to execute. |
| `language` | `string` | The interpreter to use (e.g., `"python3"`, `"node"`). |
| `options?` | [`ExecuteOptions`](/docs/api/typescript/ExecuteOptions/index.md) | Execution options. |

#### Returns

`AsyncGenerator`< | [`StreamChunk`](/docs/api/typescript/StreamChunk/index.md) | [`ExecutionResult`](/docs/api/typescript/ExecutionResult/index.md), `void`, `undefined`\>

Async iterable yielding StreamChunks followed by a final ExecutionResult.

#### Overrides

[`Sandbox`](/docs/api/typescript/Sandbox/index.md).[`executeCodeStreaming`](/docs/api/typescript/Sandbox/index.md#executecodestreaming)

---

### readFile()

```ts
readFile(path): Promise<Uint8Array<ArrayBufferLike>>;
```

Defined in: [src/sandbox/posix-shell.ts:92](https://github.com/strands-agents/harness-sdk/blob/3db1b6375bb18b5c12c42650c6fea93014b9c687/strands-ts/src/sandbox/posix-shell.ts#L92)

Read a file from the sandbox filesystem as raw bytes.

Returns `Uint8Array` to support both text and binary files. Use [readText](/docs/api/typescript/Sandbox/index.md#readtext) for a convenience wrapper that decodes to a string.

#### Parameters

| Parameter | Type | Description |
| --- | --- | --- |
| `path` | `string` | Path to the file to read. |

#### Returns

`Promise`<`Uint8Array`<`ArrayBufferLike`\>>

The file contents as raw bytes.

#### Throws

Error if the file does not exist.

#### Overrides

[`Sandbox`](/docs/api/typescript/Sandbox/index.md).[`readFile`](/docs/api/typescript/Sandbox/index.md#readfile)

---

### writeFile()

```ts
writeFile(path, content): Promise<void>;
```

Defined in: [src/sandbox/posix-shell.ts:100](https://github.com/strands-agents/harness-sdk/blob/3db1b6375bb18b5c12c42650c6fea93014b9c687/strands-ts/src/sandbox/posix-shell.ts#L100)

Write raw bytes to a file in the sandbox filesystem.

Implementations should create parent directories if they do not exist. Use [writeText](/docs/api/typescript/Sandbox/index.md#writetext) for a convenience wrapper that encodes a string.

#### Parameters

| Parameter | Type | Description |
| --- | --- | --- |
| `path` | `string` | Path to the file to write. |
| `content` | `Uint8Array` | The content to write. |

#### Returns

`Promise`<`void`\>

#### Overrides

[`Sandbox`](/docs/api/typescript/Sandbox/index.md).[`writeFile`](/docs/api/typescript/Sandbox/index.md#writefile)

---

### removeFile()

```ts
removeFile(path): Promise<void>;
```

Defined in: [src/sandbox/posix-shell.ts:111](https://github.com/strands-agents/harness-sdk/blob/3db1b6375bb18b5c12c42650c6fea93014b9c687/strands-ts/src/sandbox/posix-shell.ts#L111)

Remove a file from the sandbox filesystem.

#### Parameters

| Parameter | Type | Description |
| --- | --- | --- |
| `path` | `string` | Path to the file to remove. |

#### Returns

`Promise`<`void`\>

#### Throws

Error if the file does not exist.

#### Overrides

[`Sandbox`](/docs/api/typescript/Sandbox/index.md).[`removeFile`](/docs/api/typescript/Sandbox/index.md#removefile)

---

### listFiles()

```ts
listFiles(path): Promise<FileInfo[]>;
```

Defined in: [src/sandbox/posix-shell.ts:118](https://github.com/strands-agents/harness-sdk/blob/3db1b6375bb18b5c12c42650c6fea93014b9c687/strands-ts/src/sandbox/posix-shell.ts#L118)

List files in a sandbox directory.

Returns [FileInfo](/docs/api/typescript/FileInfo/index.md) entries with name, isDir, and size metadata. Fields `isDir` and `size` may be `undefined` if the backend cannot determine them.

#### Parameters

| Parameter | Type | Description |
| --- | --- | --- |
| `path` | `string` | Path to the directory to list. |

#### Returns

`Promise`<[`FileInfo`](/docs/api/typescript/FileInfo/index.md)\[\]>

Array of FileInfo entries for the directory contents.

#### Throws

Error if the directory does not exist.

#### Overrides

[`Sandbox`](/docs/api/typescript/Sandbox/index.md).[`listFiles`](/docs/api/typescript/Sandbox/index.md#listfiles)