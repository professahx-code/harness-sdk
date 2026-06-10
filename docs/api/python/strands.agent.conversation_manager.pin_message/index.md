Message pinning utilities for protecting messages from context eviction.

#### is\_pinned

```python
def is_pinned(messages: Messages, index: int) -> bool
```

Defined in: [src/strands/agent/conversation\_manager/pin\_message.py:28](https://github.com/strands-agents/harness-sdk/blob/main/strands-py/src/strands/agent/conversation_manager/pin_message.py#L28)

Check if a message is pinned, including tool-pair partner protection.

Returns True if the message at index is pinned, or if its adjacent tool-pair partner (toolUse/toolResult matched by toolUseId) is pinned.

**Arguments**:

-   `messages` - The full messages array.
-   `index` - The index to check.

**Returns**:

True if the message or its tool-pair partner is pinned.

#### apply\_pin\_first

```python
def apply_pin_first(messages: Messages, count: int) -> None
```

Defined in: [src/strands/agent/conversation\_manager/pin\_message.py:59](https://github.com/strands-agents/harness-sdk/blob/main/strands-py/src/strands/agent/conversation_manager/pin_message.py#L59)

Pin the first N messages in the array permanently.

**Arguments**:

-   `messages` - The messages array.
-   `count` - Number of messages from the start to pin.

#### partition\_pinned

```python
def partition_pinned(messages: Messages, start: int,
                     end: int) -> tuple[list[Message], list[Message]]
```

Defined in: [src/strands/agent/conversation\_manager/pin\_message.py:70](https://github.com/strands-agents/harness-sdk/blob/main/strands-py/src/strands/agent/conversation_manager/pin_message.py#L70)

Partition a range of messages into pinned (protected) and unpinned arrays.

**Arguments**:

-   `messages` - The full messages array.
-   `start` - Start index of the range (inclusive).
-   `end` - End index of the range (exclusive).

**Returns**:

A tuple of (pinned, unpinned) message lists.

#### pin\_message

```python
def pin_message(messages: Messages, index: int) -> None
```

Defined in: [src/strands/agent/conversation\_manager/pin\_message.py:91](https://github.com/strands-agents/harness-sdk/blob/main/strands-py/src/strands/agent/conversation_manager/pin_message.py#L91)

Pin a message so it is protected from eviction during context reduction.

Mutates the message in place by setting metadata.custom.pinned = True.

**Arguments**:

-   `messages` - The messages array.
-   `index` - The index of the message to pin.

#### unpin\_message

```python
def unpin_message(messages: Messages, index: int) -> None
```

Defined in: [src/strands/agent/conversation\_manager/pin\_message.py:108](https://github.com/strands-agents/harness-sdk/blob/main/strands-py/src/strands/agent/conversation_manager/pin_message.py#L108)

Unpin a message so it can be evicted during context reduction.

Mutates the message in place by removing the pinned flag from metadata.

**Arguments**:

-   `messages` - The messages array.
-   `index` - The index of the message to unpin.