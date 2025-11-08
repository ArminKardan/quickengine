# `SetTimeout` and `SetTimeoutSafe` in `python-worker`

## ⏱️ Example 4: `SetTimeout`

This is the Python equivalent of JavaScript's `setTimeout` using `SetTimeout` in a `python-worker` block.

```python
from libs.startup import startup
startup()
import asyncio
import sys
import threading
import time
from libs.bridge import APISpecs, App as app, MessageSpecs, SetInterval, SetTimeout
from libs.bridge import serial_generator
import json

App = app(resource="python", public=True, rest=False)

async def api(specs: APISpecs):
    if specs.cmd == "ping":
        return {"pong": True}

def timeout():
    print("hello after 1 second.")

c = SetTimeout(timeout, 1000)
c.start()

App.xmpp.onapi = api
loop = asyncio.get_event_loop()
loop.run_forever()
```

---

## ⏱️ Example 5: `SetTimeoutSafe`

`SetTimeoutSafe` works the same as `SetTimeout` but executes the callback in the main thread using `mainloop.call_soon_threadsafe`. Here's an example that runs a Nexus API call after a short delay.

```python
from libs.startup import startup
startup()
import asyncio
import sys
import threading
import time
from libs.bridge import APISpecs, App as app, MessageSpecs, SetInterval, SetTimeout, SetTimeoutSafe
from libs.bridge import serial_generator
import json

App = app(resource="python", public=True, rest=False)

async def api(specs: APISpecs):
    if specs.cmd == "ping":
        return {"pong": True}

async def runapi():
    res = await App.api(app="eaiadmin", cmd="multiply", body={"num1":3, "num2":5}, resource="default")
    if res.get("code") == 0:
        print(res.get("result"))

SetTimeoutSafe(runapi, 10).start()

App.xmpp.onapi = api
loop = asyncio.get_event_loop()
loop.run_forever()
```

---

## ⛔ Example 6: Cancelling `SetTimeout`

Just like JavaScript’s `clearTimeout`, you can cancel a timeout in `python-worker` by calling `cancel()`.

```python
def timeout():
    print("hello after 1 second.")

c = SetTimeout(timeout, 1000)
c.start()
SetTimeout(c.cancel, 500).start()
```

In this case, the first timeout is cancelled before it fires, so `hello after 1 second.` is never printed.