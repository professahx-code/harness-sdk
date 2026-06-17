```ts
type MultiAgentSaveLatestStrategy = "node" | "invocation";
```

Defined in: [src/session/session-manager.ts:53](https://github.com/strands-agents/harness-sdk/blob/d88911386ffd4b5f924c7b896ad24f288632baec/strands-ts/src/session/session-manager.ts#L53)

Controls when `snapshot_latest` is saved for multi-agent orchestrators.

-   `'node'`: after every node invocation completes (default; enables resume from the last completed node after a crash or restart)
-   `'invocation'`: after every orchestrator invocation completes (lower I/O, but only captures state at orchestrator invocation boundaries)