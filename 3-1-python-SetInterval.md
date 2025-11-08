
# Periodic Task Execution in `python-worker` (QE System)

In QE's `python-worker`, periodic task execution is handled using `SetInterval` or `SetIntervalSafe` classes instead of standard Python techniques. This ensures better compatibility and safety with the asynchronous system design of QE workers.

---

## ✅ Example 1: Using `SetInterval`

This example prints `hello` every 2 seconds:

```python
from libs.startup import startup
startup()
import asyncio
import sys
import threading
import time
from libs.bridge import APISpecs, App as app, MessageSpecs, SetInterval
from libs.bridge import serial_generator
import json

App = app(resource="python", public=True, rest=False)

async def api(specs: APISpecs):
    if specs.cmd == "ping":
        return {"pong": True}

def interval():
    print("hello")
    
SetInterval(interval, 2000).start()

App.xmpp.onapi = api
loop = asyncio.get_event_loop()
loop.run_forever()
```

---

## ✅ Example 2: Using `SetIntervalSafe`

`SetIntervalSafe` is a thread-safe version that uses `mainloop.call_soon_threadsafe()` internally, ideal for updating UI or sensitive resources from multiple threads.

```python
from libs.bridge import SetIntervalSafe

def interval():
    print("hello")

SetIntervalSafe(interval, 2000).start()
```

---

## ✅ Example 3: Using `SetInterval` with `stop()`

This example prints `hello` five times and then stops:

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

counter = 0
def interval():
    global counter
    counter += 1
    print("hello")
    if counter >= 5:
        print("interval cleared.")
        c.stop()
    
c = SetInterval(interval, 1000)
c.start()

App.xmpp.onapi = api
loop = asyncio.get_event_loop()
loop.run_forever()
```

---

These interval utilities make it easy to perform regular background tasks in a robust, thread-safe manner tailored to the QE ecosystem.
