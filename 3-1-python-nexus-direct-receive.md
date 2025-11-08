# Nexus Direct Receive (Python Worker):
Here we set a sample Python worker to listen to directs:

```python
import asyncio
from libs.bridge import NexusAPISpecs, App as AppClass, NexusMessageSpecs
from libs.bridge import setInterval, clearInterval, setTimeout

App = AppClass(public=True, rest=False)

@App.nexus.Direct()
async def f(specs: NexusMessageSpecs):
    print("Direct:", specs.body)


loop = asyncio.get_event_loop()
loop.run_forever()

```

> Note that body can only be `list` or a `dictionary` no any other types are supported.

Here is the specs specifications:

```python
@dataclass
class NexusMessageSpecs:
    fromjid: str
    body: str | dict
    role: str
    channel: str
    app: str
    uid: str
    resource: str
    itsme: bool
    itsbro: bool
```