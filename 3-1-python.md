
# Python Worker Guide

The Python Worker block in QE is designed for executing specialized or distributed tasks that are not feasible directly via a [Admin Panel]() or [XWebsite](). This includes scenarios such as running OS-level commands, managing hardware interfaces, or balancing workloads across multiple systems. The worker processes the command and returns the results.


## Typical use cases:
- Running OS-level commands
- Load-balanced processing across multiple systems
- AI Models handling.

## Minimal Structure

Here’s the minimal structure required for a QE Python Worker:

```python
import asyncio
from libs.bridge import NexusAPISpecs, App as AppClass, NexusMessageSpecs
from libs.bridge import setInterval, clearInterval, setTimeout

App = AppClass(public=True, rest=False)


loop = asyncio.get_event_loop()
loop.run_forever()

```
## Examples:

- [How to Receive a Nexus API message from Python worker](https://qepal.com/docs/3-1-python-nexus-api-receive.md)
- [How to Send a Nexus API message from Python worker](https://qepal.com/docs/3-1-python-nexus-api-send.md)
- [How to Receive Nexus Channel messages by a Python worker](https://qepal.com/docs/3-1-python-nexus-channel-receive.md)
- [How to Send Data to a Nexus Channel in Python worker](https://qepal.com/docs/3-1-python-nexus-channel-send.md)
- [How to Receive Data using Nexus Direct by a Python worker](https://qepal.com/docs/3-1-python-nexus-direct-receive.md)
- [How to Send Data to a Nexus Direct in Python worker](https://qepal.com/docs/3-1-python-nexus-direct-send.md)
- [How to Find Workers using Nexus Find in a Python worker](https://qepal.com/docs/3-1-python-nexus-find.md)
- [How to access Service Database (udb)](https://qepal.com/3-1-python-udb.md)
- [How to start a RestAPI Server in a Python worker](https://qepal.com/docs/3-1-python-rest-server.md)
- [How to have Periodic tasks in Python Worker](https://qepal.com/docs/3-1-python-SetInterval.md)
- [How to have Delayed tasks in Python Worker](https://qepal.com/docs/3-1-python-SetTimeout.md)
- [How to upload files using Python worker](https://qepal.com/docs/3-1-python-uploader.md)