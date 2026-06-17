A :class:`~strands.memory.types.MemoryStore` backed by Amazon Bedrock Knowledge Bases.

Supports semantic search via `Retrieve` and document ingestion via `IngestKnowledgeBaseDocuments` for `CUSTOM` and `S3` data sources.

## BedrockKnowledgeBaseStore

```python
class BedrockKnowledgeBaseStore(MemoryStore)
```

Defined in: [src/strands/vended\_memory\_stores/bedrock\_knowledge\_base/store.py:65](https://github.com/strands-agents/harness-sdk/blob/main/strands-py/src/strands/vended_memory_stores/bedrock_knowledge_base/store.py#L65)

A :class:`~strands.memory.types.MemoryStore` backed by Amazon Bedrock Knowledge Bases.

Supports semantic search via `Retrieve` and document ingestion via `IngestKnowledgeBaseDocuments` for `CUSTOM` and `S3` data sources.

**Example**:

```python
from strands.vended_memory_stores.bedrock_knowledge_base import BedrockKnowledgeBaseStore

store = BedrockKnowledgeBaseStore(
    config=\{
        "knowledge_base_id": "KB123",
        "data_source_type": "CUSTOM",
        "data_source_id": "DS456",
    },
    name="preferences",
    scope="user-abc",
    writable=True,
)

results = await store.search("what are my preferences?")
result = await store.add("User prefers dark mode")
```

#### \_\_init\_\_

```python
def __init__(**store_config: Unpack[BedrockKnowledgeBaseStoreConfig]) -> None
```

Defined in: [src/strands/vended\_memory\_stores/bedrock\_knowledge\_base/store.py:91](https://github.com/strands-agents/harness-sdk/blob/main/strands-py/src/strands/vended_memory_stores/bedrock_knowledge_base/store.py#L91)

Initialize the store.

**Arguments**:

-   `**store_config` - See :class:`BedrockKnowledgeBaseStoreConfig`.

**Raises**:

-   `ValueError` - If `max_search_results` is less than 1, or (when `writable`) if the write configuration is invalid.

#### search

```python
async def search(query: str,
                 options: SearchOptions | None = None) -> list[MemoryEntry]
```

Defined in: [src/strands/vended\_memory\_stores/bedrock\_knowledge\_base/store.py:145](https://github.com/strands-agents/harness-sdk/blob/main/strands-py/src/strands/vended_memory_stores/bedrock_knowledge_base/store.py#L145)

Search the knowledge base for entries matching the query.

**Arguments**:

-   `query` - The search query text.
-   `options` - Optional search configuration.

**Returns**:

Matching memory entries ordered by relevance. Each entry’s `metadata` includes user-provided attributes plus two reserved synthetic keys: `_relevance_score` (number) and `_source_location` (Bedrock retrieval location object).

**Raises**:

-   `ValueError` - If `options.max_search_results` is less than 1.

#### add

```python
async def add(
        content: str,
        metadata: Metadata | None = None) -> BedrockKnowledgeBaseAddResult
```

Defined in: [src/strands/vended\_memory\_stores/bedrock\_knowledge\_base/store.py:205](https://github.com/strands-agents/harness-sdk/blob/main/strands-py/src/strands/vended_memory_stores/bedrock_knowledge_base/store.py#L205)

Ingest `content` (with optional `metadata`) into the knowledge base.

Only `CUSTOM` and `S3` data sources support this. Requires `data_source_id` (and, for `S3`, an `s3` config).

**Arguments**:

-   `content` - The text content to ingest.
-   `metadata` - Optional metadata attributes to attach to the document.

**Returns**:

The document identifier (UUID for `CUSTOM`, `s3://` URI for `S3`).

**Raises**:

-   `ValueError` - If the store is not writable or `content` is empty/whitespace.