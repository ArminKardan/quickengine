
# QE `python-worker` Guide

## Overview

The `python-worker` block in QE is designed for executing specialized or distributed tasks that are not feasible directly via a `Admin Panel`. This includes scenarios such as running OS-level commands, managing hardware interfaces, or balancing workloads across multiple systems. The worker processes the command and returns the results.

---

## 🧭 Getting Started

When a `topuser` creates a project, development files can be downloaded. Once extracted, follow these steps:

1. Run `yarn manager` to start the QE environment manager.
2. Open the Explore settings by clicking the **date ribbon** in the top-right corner of the Explore poster.
3. You’ll see blocks such as:
   - `wpy[app-name]` (e.g., `wpytest`) with a Python icon.
   - A `vscode` icon (indicates active development integration).

4. Click the `vscode` icon to open the project in Visual Studio Code at the correct path.
5. Open the `wpy[app]` folder, locate and open `run.ts`.

> ⚠️ Each `python-worker` must have a **unique** resource ID prefixed with `py`, e.g., `pyworker1`, `pyimager`, `pyswitch`.

---

## 🧱 Minimal Structure

Here’s the minimal structure required for a QE `python-worker`:

```python
from libs.startup import startup
startup()
import asyncio
from libs.bridge import APISpecs, App as app

App = app(resource="python", public=True, rest=False)

async def api(specs: APISpecs):
    if specs.cmd == "ping":
        return {"pong": True}

#TODO Codes

App.xmpp.onapi = api

loop = asyncio.get_event_loop()
loop.run_forever()
```

> 🔄 The `api` function handles all incoming Nexus API calls. Handling the `"ping"` request is mandatory in every QE worker.

---

## ⚙️ Running in Development Mode

> 🖥️ Supported only on **Windows 10+**

### Prerequisites

- [x] Miniconda **must** be installed (even if Anaconda is installed).
- [x] `yarn manager` is running.

### Steps

1. Open the Explore settings (via the date ribbon).
2. Click on the Python worker (`wpy[app]`).
3. An environment named `evox` is automatically created if it doesn't exist.
   - Uses Python version `3.12.8`
   - Installs all required packages automatically.
4. Visual Studio Code opens in the correct environment and directory.
5. Open `run.py`, then click ▶️ (play button) in VSCode to start the worker.
6. To stop execution:
   - Press `Ctrl+C` in the terminal, **or**
   - Click the bin/trash icon in the terminal window.

---

## ➕ Installing Additional Libraries

To install extra Python libraries:

1. Run `run.py` once to generate the `terminal.bat` file inside the `python-worker` folder.
2. Double-click `terminal.bat` — this opens the **Miniconda terminal** in the `evox` environment.
3. Use `pip` or `conda` to install any additional libraries:

```bash
pip install pillow
```

> 📦 Installed packages are shared across all `python-worker` projects under the same environment.

---

## ✅ Summary

- Each `python-worker` must respond to the `ping` command.
- Development runs inside the `evox` Conda environment.
- `yarn manager` and `miniconda` are required.
- Installed libraries via `terminal.bat` apply globally to QE Python workers.

