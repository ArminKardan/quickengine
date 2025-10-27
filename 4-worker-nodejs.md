# `nodejs-worker` Block

## 🧩 Description
Some tasks—such as executing system-level commands or performing distributed workloads across multiple systems—cannot be handled directly by a `Admin Panel`. In such cases, worker blocks (e.g., `nodejs-worker`, `python-worker`, etc.) are used. These blocks receive commands and data, perform the task independently, and return the result to the system.

**Typical use cases:**
- Running OS-level commands
- Load-balanced processing across multiple systems

## 🚀 How to Start

1. **Project Setup**  
   After a `topuser` creates a project, they can download its development files.

2. **Initialize Manager**  
   Extract the files and run:
   ```bash
   yarn manager
   ```

3. **Open Explore Settings**  
   In the QE Explore interface, navigate to the **Settings** tab.

4. **Locate Worker Blocks**  
   You’ll see multiple entries like `w[app]` with a Node.js icon. For example, if your app is called `test`, look for `wtest`.

5. **Open VS Code**  
   Click the blue `vscode` icon in Explore Settings. If `yarn manager` is working correctly, VS Code should launch in the project directory.

6. **Edit the Worker Script**  
   In VS Code, open the `w[app]` folder and then `run.ts`.

7. **Minimum Working Example**  
   Here's a minimal setup to get a worker connected:

   ```ts
   import { App } from './libs/bridge';
   (async () => {
       console.clear()
       await App.Init(false);
       await App.initUDB();

       await App.Connect({
           resource: process.env.RESOURCE || "default",
           image: "/files/app/robot.webp",
       });

       console.log("[nexus] connected.");


       //TODO CODES will be here

       App.on("ping", async (specs) => {
           console.log("ping request from:", specs.uid);
           return { code: 0, pong: true };
       });
   })();
   ```

8. **Start the Worker**  
   Back in Explore Settings, click on the `w[app]` Node.js icon to run the worker locally.


Available global functions in NodeJS worker are:

- `api`
Sending rest api request (GET/POST) with json payload.
- `MD5`
Gets an string or buffer and gives a MD5 hex string
- `SHA256`
Gets an string or buffer and gives a SHA256 hex string
- `serialgenerator`
Making random string by given length
- `encryptor`
Encrypt a string by password
- `decryptor`
Decrypt string using password
- `sleep`
Making Delay on async functions

It also has built-in:

- Telegram library (with build-in proxy)

- Internal puppeteer for browser control

- built in `express` for rest API communication.

- `udb` access to Universal explore database.

- Third party library installation capability