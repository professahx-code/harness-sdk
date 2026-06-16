Cross-session memory retrieval and storage for agents.

## MemoryManager

```python
class MemoryManager(Plugin)
```

Defined in: [src/strands/memory/memory\_manager.py:69](https://github.com/strands-agents/harness-sdk/blob/main/strands-py/src/strands/memory/memory_manager.py#L69)

Provides cross-session memory retrieval and storage for agents.

**Example**:

```python
from strands import Agent
from strands.memory import MemoryManager

memory_manager = MemoryManager(stores=[my_store])
agent = Agent(model=model, memory_manager=memory_manager)
agent("Remember I prefer dark mode")

results = await memory_manager.search("user preferences")
```

#### \_\_init\_\_

```python
def __init__(stores: list[MemoryStore],
             search_tool_config: MemoryToolConfig | bool = True,
             add_tool_config: MemoryAddToolConfig | bool = False,
             injection: MemoryInjectionConfig | bool = True) -> None
```

Defined in: [src/strands/memory/memory\_manager.py:87](https://github.com/strands-agents/harness-sdk/blob/main/strands-py/src/strands/memory/memory_manager.py#L87)

Initialize the memory manager.

**Arguments**:

-   `stores` - One or more memory stores to manage.
-   `search_tool_config` - Search tool configuration. `True` (default) registers a `search_memory` tool with default name/description; a :class:`MemoryToolConfig` customizes it; `False` disables it.
-   `add_tool_config` - Add tool configuration. `False` (default) disables the add tool; `True` lets it write to all writable stores; a :class:`MemoryAddToolConfig` restricts/customizes it.
-   `injection` - Memory context injection. `True` (default) uses the default injection settings; a :class:`MemoryInjectionConfig` customizes retrieval, timing, and formatting; `False` disables it. When enabled, retrieved memory is folded into the model input before each call without touching durable history.

**Raises**:

-   `ValueError` - If `stores` is empty, a store name is duplicated, a writable store has no write sink, an extraction config is misconfigured, or the add tool is enabled/scoped against stores that cannot accept discrete `add` writes.

#### tools

```python
@property
def tools() -> list[AgentTool]
```

Defined in: [src/strands/memory/memory\_manager.py:256](https://github.com/strands-agents/harness-sdk/blob/main/strands-py/src/strands/memory/memory_manager.py#L256)

Tools registered by this plugin: search/add plus any store-provided tools.

Widens the base :class:`~strands.plugins.plugin.Plugin` annotation because a store’s `get_tools` may contribute any :class:`~strands.types.tools.AgentTool`.

#### search

```python
async def search(
        query: str,
        options: MemorySearchOptions | None = None) -> list[MemoryEntry]
```

Defined in: [src/strands/memory/memory\_manager.py:265](https://github.com/strands-agents/harness-sdk/blob/main/strands-py/src/strands/memory/memory_manager.py#L265)

Search stores for entries matching the query.

Unscoped: searches all configured stores when `options.stores` is omitted. Results are attributed to their store via `store_name` and concatenated in target order.

**Raises**:

-   `ValueError` - If a named store is not found (raised before querying).

#### add

```python
async def add(content: str, options: MemoryAddOptions | None = None) -> None
```

Defined in: [src/strands/memory/memory\_manager.py:329](https://github.com/strands-agents/harness-sdk/blob/main/strands-py/src/strands/memory/memory_manager.py#L329)

Add content to writable stores.

Unscoped: targets all configured writable stores. Target stores are validated first, then writes are awaited concurrently; per-store failures are logged and surfaced as an :class:`~strands.types.exceptions.AggregateMemoryError`.

**Raises**:

-   `ValueError` - If a named store is not found or is read-only, or if no writable store matched.
-   `AggregateMemoryError` - If any targeted store write fails.

#### init\_agent

```python
def init_agent(agent: Agent) -> None
```

Defined in: [src/strands/memory/memory\_manager.py:539](https://github.com/strands-agents/harness-sdk/blob/main/strands-py/src/strands/memory/memory_manager.py#L539)

Initialize the plugin with the agent.

Wires up two independent behaviors:

-   **Extraction**: for any store configured with an `ExtractionConfig`, buffers conversation messages and attaches each store’s triggers. A no-op when no store uses extraction. Extraction runs in the background; the synchronous `Agent(...)` entry point awaits :meth:`flush` after each invocation so writes persist, and callers driving the agent through their own event loop should await :meth:`flush` at a shutdown boundary.
-   **Injection**: when enabled, registers an `InvokeModelStage` middleware that folds retrieved memory into the model input for each call without touching durable history. A no-op when injection is disabled.

#### flush

```python
async def flush() -> None
```

Defined in: [src/strands/memory/memory\_manager.py:690](https://github.com/strands-agents/harness-sdk/blob/main/strands-py/src/strands/memory/memory_manager.py#L690)

Save every store’s remaining messages and wait for all saves to finish.

A no-op when no store has extraction configured. Drains automatic extraction only; `add_memory` fire-and-forget writes are not awaited here.