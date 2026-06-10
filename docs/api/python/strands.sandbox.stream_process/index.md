Spawn a process and stream its stdout/stderr as an async generator.

Mirrors `strands-ts/src/sandbox/stream-process.ts`.

The shared process-supervision engine behind the shell-based backends (Docker, SSH): a backend builds an argv, and this spawns the process, streams its output as :class:`StreamChunk` objects, and yields a final :class:`ExecutionResult`.

Cancellation is cooperative — cancelling the consuming task (or closing the generator) runs the cleanup in `finally`, which kills the process. `timeout` is wall-clock: measured from spawn and not reset by ongoing output.

#### stream\_process

```python
async def stream_process(
    program: str,
    args: list[str],
    *,
    timeout: float | None = None,
    enoent_message: str | None = None
) -> AsyncGenerator[StreamChunk | ExecutionResult, None]
```

Defined in: [src/strands/sandbox/stream\_process.py:41](https://github.com/strands-agents/harness-sdk/blob/main/strands-py/src/strands/sandbox/stream_process.py#L41)

Spawn a command and stream its stdout/stderr, yielding the final result.

Yields :class:`StreamChunk` objects as output arrives, then a single final :class:`ExecutionResult`. Signal termination maps to `128 + signal` (e.g. SIGKILL -> 137). Cancelling the consuming task kills the process.

**Arguments**:

-   `program` - The binary to spawn (e.g. `"docker"`, `"ssh"`).
-   `args` - Arguments to pass to the binary.
-   `timeout` - Maximum wall-clock execution time in seconds, measured from spawn (not reset by output). `None` means no timeout.
-   `enoent_message` - Message to surface as `stderr` (with exit code 127) when `program` is not on PATH. If `None`, the underlying :class:`FileNotFoundError` propagates instead.

**Yields**:

:class:`StreamChunk` objects for output, then a final :class:`ExecutionResult`.

**Raises**:

-   `TimeoutError` - If execution exceeds `timeout` seconds.
-   `FileNotFoundError` - If `program` is not found and `enoent_message` is `None`.