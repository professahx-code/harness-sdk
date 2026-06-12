Base class for intervention handlers.

Handlers override the lifecycle methods they care about. Default implementations return Proceed. The framework detects which methods are overridden and only registers hook callbacks for those.

#### OnError

What to do when a handler throws during evaluation.

-   `'throw'` — rethrow the error (default, safest: a broken policy check blocks execution)
-   `'proceed'` — log the error and continue as if the handler returned Proceed. **This mode is fail-open**: a broken handler silently stops enforcing its policy. Use only when availability matters more than enforcement.
-   `'deny'` — log the error and treat it as a Deny (fail-closed)

## InterventionHandler

```python
class InterventionHandler(ABC)
```

Defined in: [src/strands/interventions/handler.py:31](https://github.com/strands-agents/harness-sdk/blob/main/strands-py/src/strands/interventions/handler.py#L31)

Base class for intervention handlers.

Subclasses must define a `name` attribute and override the lifecycle methods they care about at the **class level**. The framework detects which methods are overridden and only calls those. Instance-level assignments (e.g., `handler.before_tool_call = my_func`) are not detected.

**Example**:

```python
class CedarAuth(InterventionHandler):
    name = "cedar-auth"

    def before_tool_call(self, event):
        if not self.is_authorized(event):
            return Deny(reason="not authorized")
        return Proceed()
```

#### name

```python
@property
@abstractmethod
def name() -> str
```

Defined in: [src/strands/interventions/handler.py:53](https://github.com/strands-agents/harness-sdk/blob/main/strands-py/src/strands/interventions/handler.py#L53)

Unique name identifying this handler.

#### on\_error

```python
@property
def on_error() -> OnError
```

Defined in: [src/strands/interventions/handler.py:58](https://github.com/strands-agents/harness-sdk/blob/main/strands-py/src/strands/interventions/handler.py#L58)

What to do when this handler throws. Defaults to ‘throw’.

#### before\_invocation

```python
def before_invocation(event: BeforeInvocationEvent,
                      **kwargs: Any) -> Proceed | Deny | Guide | Transform
```

Defined in: [src/strands/interventions/handler.py:62](https://github.com/strands-agents/harness-sdk/blob/main/strands-py/src/strands/interventions/handler.py#L62)

Called before an agent invocation begins.

#### before\_tool\_call

```python
def before_tool_call(
        event: BeforeToolCallEvent,
        **kwargs: Any) -> Proceed | Deny | Guide | Confirm | Transform
```

Defined in: [src/strands/interventions/handler.py:66](https://github.com/strands-agents/harness-sdk/blob/main/strands-py/src/strands/interventions/handler.py#L66)

Called before a tool is executed.

#### after\_tool\_call

```python
def after_tool_call(event: AfterToolCallEvent,
                    **kwargs: Any) -> Proceed | Transform
```

Defined in: [src/strands/interventions/handler.py:72](https://github.com/strands-agents/harness-sdk/blob/main/strands-py/src/strands/interventions/handler.py#L72)

Called after a tool execution completes.

#### before\_model\_call

```python
def before_model_call(event: BeforeModelCallEvent,
                      **kwargs: Any) -> Proceed | Deny | Guide | Transform
```

Defined in: [src/strands/interventions/handler.py:76](https://github.com/strands-agents/harness-sdk/blob/main/strands-py/src/strands/interventions/handler.py#L76)

Called before the model is invoked.

#### after\_model\_call

```python
def after_model_call(event: AfterModelCallEvent,
                     **kwargs: Any) -> Proceed | Guide | Transform
```

Defined in: [src/strands/interventions/handler.py:80](https://github.com/strands-agents/harness-sdk/blob/main/strands-py/src/strands/interventions/handler.py#L80)

Called after the model invocation completes.