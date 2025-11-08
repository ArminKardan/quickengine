
# REST API in `python-worker` on QE Platform

## Overview

In the QE system, `python-worker` supports exposing REST endpoints using a built-in integration with **FastAPI** via `App.rest`. This allows developers to run HTTP servers directly within the worker, typically on port `8000`, and define routes (`GET`, `POST`, etc.) as needed.

This capability is helpful when:
- Exposing diagnostic or control endpoints
- Accepting data from other QE components or external tools
- Running Admin Panel-like REST interfaces inside a worker process

> Note: This REST interface is separate from the internal **Nexus API**. The Nexus API is handled by `App.api` and `App.xmpp.onapi`, not `App.rest`.

---

## Enabling REST API

To enable the REST API in a `python-worker`, you need to pass a `rest` port (e.g., `8000`) when initializing the app:

```python
App = app(resource="python", public=True, rest=8000)
```

This makes the worker listen on the specified port for HTTP requests using FastAPI under the hood.

---

## Defining Routes

### GET Example

You can define a simple `GET` route at `/` like this:

```python
@App.rest.get("/")
def root():
    return {"code": 0}
```

This responds to HTTP `GET /` with a JSON response `{ "code": 0 }`.

### POST Example with JSON Input

You can define a `POST` route that accepts JSON input by using FastAPI's `Request` object:

```python
from fastapi import Request

@App.rest.post("/")
async def root(req: Request):
    data = await req.json()
    print(f"Received POST: {data}")
    return {"code": 0}
```

This prints the received data and returns a simple success response.

---

## Sending REST Requests

Inside `python-worker`, you can also send HTTP requests using the `requests` package. For example, to send a `POST` request:

```python
import requests as r

response = r.post("http://localhost:8000", json={"data": 1000})
print(response.json())
```

This sends a JSON payload to the local worker's REST endpoint and prints the JSON response.

---

## Summary

| Feature           | Method                                      | Notes                                |
|-------------------|---------------------------------------------|--------------------------------------|
| Enable REST       | `app(..., rest=8000)`                       | Enables FastAPI on port 8000         |
| Define route (GET)| `@App.rest.get("/")`                        | Returns data for `GET /`             |
| Define route (POST)| `@App.rest.post("/")` + `await req.json()`| Handles JSON data from POST          |
| Call REST         | `requests.post(...).json()`                 | Sends REST requests within worker    |
| Nexus API         | `App.api`, `App.xmpp.onapi`                 | Internal command/data system         |
