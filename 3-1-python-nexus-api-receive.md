# Nexus API Receive (Python Worker):
Here we set a sample Python worker to listen to nexus api in command `samplecmd`:


```python
import asyncio
from libs.bridge import NexusAPISpecs, App as AppClass, NexusMessageSpecs
from libs.bridge import setInterval, clearInterval, setTimeout

App = AppClass(public=True, rest=False)

@App.nexus.API("samplecmd")
async def f(specs: NexusAPISpecs):
    return {"code": 0, "myval": "Hi from Python Worker!"}


loop = asyncio.get_event_loop()
loop.run_forever()

```
Here is the specs specifications:

```python
@dataclass
class NexusAPISpecs:
    cmd: str
    uid: str
    role: str
    app: str
    resource: str
    servid: ObjectId
    servsecret: str
    body: dict
```