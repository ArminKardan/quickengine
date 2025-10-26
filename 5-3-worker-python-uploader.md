# Uploading Content to CDN via `python-worker` in QE

In the QE ecosystem, the `python-worker` provides a convenient method to upload files or text to a content delivery network (CDN) using the `App.uploader()` method. This is useful for sharing files or storing logs and generated content.

---

## Example 1: Upload Text to CDN

You can upload any text content using `App.uploader`. Below is a complete example that uploads a plain text message to the CDN for 1 hour:

```python
from fastapi import Request
from libs.startup import startup

startup()
import asyncio
import sys
import threading
import time
from libs.bridge import (
    APISpecs,
    App as app,
    MessageSpecs,
    SetInterval,
    SetIntervalSafe,
    SetTimeout,
    SetTimeoutSafe,
)
from libs.bridge import serial_generator
import json
import requests as r

App = app(resource="python", public=True, rest=False)

async def api(specs: APISpecs):
    if specs.cmd == "ping":
        return {"pong": True}

url = App.uploader("Hello, this is test content.", 3600, "txt")
print("File uploaded to:", url)

App.xmpp.onapi = api
loop = asyncio.get_event_loop()
loop.run_forever()
```

### Parameters for `App.uploader`:

```python
App.uploader(content, lifetime_in_seconds, extension)
```

- `content`: The content to be uploaded. This can be text or binary data.
- `lifetime_in_seconds`: The duration (in seconds) for which the file will remain on the server. Set to `0` to make it permanent.
- `extension`: File extension (e.g., `"txt"`, `"jpg"`, `"log"`), which defines the content type on upload.

---

## Example 2: Upload an Image to CDN

You can also upload binary files like images. Here’s how to upload a JPEG image:

```python
with open('./1.jpg', 'rb') as f:
    binary_content = f.read()
    url = App.uploader(binary_content , 300, "jpg")
    print("File uploaded to:", url)
```

This will upload the image for 5 minutes (300 seconds). After that, it will automatically be removed by the server.

---

## Notes

- `App.uploader` is fully integrated with QE's file system and CDN infrastructure.
- It's compatible with both text and binary content.
- All uploaded files will be accessible through a public CDN URL.