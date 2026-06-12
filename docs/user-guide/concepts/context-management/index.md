As conversations grow, your agent’s context window fills with messages, tool results, and system prompts. Without management, this leads to token limit errors, degraded performance, and loss of relevant information.

The SDK provides several layers of context management that you can use independently or together.

## Automatic context management

For most agents with multi-turn conversations, you don’t need to configure conversation management and context offloading separately. Pass `context_manager="auto"` (Python) or `contextManager: "auto"` (TypeScript) and the SDK wires up both with tuned defaults:

(( tab "Python" ))
```python
from strands import Agent

agent = Agent(context_manager="auto")
```
(( /tab "Python" ))

(( tab "TypeScript" ))
```typescript
import { Agent } from '@strands-agents/sdk'

const agent = new Agent({
  contextManager: 'auto',
})
```
(( /tab "TypeScript" ))

### What it sets up

This composes two components whose defaults scored highest across [ContextBench](https://arxiv.org/abs/2602.05892) evaluations relative to other Strands Agent configurations:

-   **SummarizingConversationManager** (summary ratio of 0.3, compression threshold of 0.85): proactively summarizes older messages before the context window fills, preserving key information while freeing space for new turns.
-   **ContextOffloader plugin** (max result tokens of 1,500, preview tokens of 750): intercepts large tool results at execution time, stores them externally, and keeps a truncated preview in context. Registers a `retrieve_offloaded_content` tool so the agent can fetch full content on demand.

For full details on each component, see [Conversation Management](/docs/user-guide/concepts/agents/conversation-management/index.md#summarizingconversationmanager) and [Context Offloader](/docs/user-guide/concepts/plugins/context-offloader/index.md).

### Combining with explicit configuration

Your own settings take precedence when you need fine-grained control:

-   **Custom conversation manager**: If you also pass `conversation_manager` / `conversationManager`, your manager replaces the auto-composed `SummarizingConversationManager`. The SDK still adds the `ContextOffloader` plugin.
-   **Existing ContextOffloader**: If your `plugins` list already contains a `ContextOffloader` instance, no duplicate is added. Your configuration is preserved.

(( tab "Python" ))
```python
from strands import Agent
from strands.agent.conversation_manager import (
    SlidingWindowConversationManager,
)

# Your conversation manager is used;
# ContextOffloader is still added automatically
agent = Agent(
    context_manager="auto",
    conversation_manager=SlidingWindowConversationManager(
        window_size=30,
    ),
)
```
(( /tab "Python" ))

(( tab "TypeScript" ))
```typescript
import {
  Agent,
  SlidingWindowConversationManager,
} from '@strands-agents/sdk'

// Your conversation manager is used;
// ContextOffloader is still added automatically
const agent = new Agent({
  contextManager: 'auto',
  conversationManager: new SlidingWindowConversationManager({
    windowSize: 30,
  }),
})
```
(( /tab "TypeScript" ))

### Limitations

**Stateful models**: Stateful models manage conversation state server-side. Setting `context_manager="auto"` with a stateful model raises a `ValueError` (Python) or `Error` (TypeScript).

The auto-composed offloader uses in-memory storage that does not persist across process restarts. If your agent uses session management and needs durable offloaded content, configure an explicit `ContextOffloader` with `FileStorage` or `S3Storage`. See [Storage Backends](/docs/user-guide/concepts/plugins/context-offloader/index.md#storage-backends).

## Related pages

- [Context Offloader](/docs/user-guide/concepts/plugins/context-offloader/index.md) (2 shared tags)
- [Conversation Management](/docs/user-guide/concepts/agents/conversation-management/index.md) (2 shared tags)
- [Coherence Evaluator](/docs/user-guide/evals-sdk/evaluators/coherence_evaluator/index.md) (1 shared tag)
- [Conciseness Evaluator](/docs/user-guide/evals-sdk/evaluators/conciseness_evaluator/index.md) (1 shared tag)
- [Goal Success Rate Evaluator](/docs/user-guide/evals-sdk/evaluators/goal_success_rate_evaluator/index.md) (1 shared tag)
- [Helpfulness Evaluator](/docs/user-guide/evals-sdk/evaluators/helpfulness_evaluator/index.md) (1 shared tag)
- [Interactions Evaluator](/docs/user-guide/evals-sdk/evaluators/interactions_evaluator/index.md) (1 shared tag)
- [Output Evaluator](/docs/user-guide/evals-sdk/evaluators/output_evaluator/index.md) (1 shared tag)
- [Skills](/docs/user-guide/concepts/plugins/skills/index.md) (1 shared tag)
- [User Simulation](/docs/user-guide/evals-sdk/simulators/user_simulation/index.md) (1 shared tag)
