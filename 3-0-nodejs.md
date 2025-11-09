# NodeJS Block
Some tasks—such as executing system-level commands or performing distributed workloads across multiple systems—cannot be handled directly by a `Admin Panel` or `XWebsite`. In such cases, worker blocks (e.g., NodeJS, [Python](https://qepal.com/docs/3-1-python.md), etc.) are used. These blocks receive commands and data, perform the task independently, and return the result to the system.

## Typical use cases:
- Running OS-level commands
- Load-balanced processing across multiple systems

## Minimum Working Example 
   Here's a minimal setup to get a worker connected:

   ```ts
   import { App } from './libs/bridge';
   (async () => {
       console.clear()
       await App.Init(false);
       await App.initUDB();
       await App.Connect({});

       //TODO CODES will be here
   
   })();
   ```

Available global functions in NodeJS worker are:

- [MD5](https://qepal.com/docs/javascript-globals-md5.md) — Hash functions.
- [SHA256](https://qepal.com/docs/javascript-globals-sha256.md) — Hash functions.
- [sleep](https://qepal.com/docs/javascript-globals-sleep.md) — Async delay.
- [udb](https://qepal.com/docs/1-15-qe-nodejs-udb.md) Service's MongoDB Database.
- [api](https://qepal.com/docs/back-globals-api.md) — Unified GET/POST fetcher.
- [serialgenerator](https://qepal.com/docs/javascript-globals-serialgenerator.md) — If we need Random string generator.
- [sleep](https://qepal.com/docs/javascript-globals-sleep.md) — Async delay.
- [encryptor](https://qepal.com/docs/javascript-globals-encryptdecrypt.md) — If we need  Symmetric encryption.
- [decryptor](https://qepal.com/docs/javascript-globals-encryptdecrypt.md) — If we need  Symmetric encryption.
- [FAtoENRatio](https://qepal.com/docs/javascript-globals-FAtoENRatio.md) — If we need  Symmetric encryption.

## Examples:

- [How to Receive a Nexus API message from NodeJS worker](https://qepal.com/docs/3-0-nodejs-nexus-api-receive.md)
- [How to Send a Nexus API message from NodeJS worker](https://qepal.com/docs/3-0-nodejs-nexus-api-send.md)
- [How to Receive Data from a Nexus Channel by a NodeJS worker](https://qepal.com/docs/3-0-nodejs-nexus-chennel-receive.md)
- [How to Send Data to a Nexus Channel in NodeJS worker](https://qepal.com/docs/3-0-nodejs-nexus-channel-send.md)
- [How to Receive Data using Nexus Direct by a NodeJS worker](https://qepal.com/docs/3-0-nodejs-nexus-direct-receive.md)
- [How to Send Data to a Nexus Direct in NodeJS worker](https://qepal.com/docs/3-0-nodejs-nexus-direct-send.md)
- [How to Find Workers using Nexus Find in a NodeJS worker](https://qepal.com/docs/3-0-nodejs-nexus-find.md)
- [How to access Service Database (udb)](https://qepal.com/3-0-nodejs-udb.md)
- [How to start a RestAPI Server in a NodeJS worker](https://qepal.com/docs/3-0-nodejs-rest-server.md)
- [How to upload files using NodeJS worker](https://qepal.com/docs/3-0-nodejs-uploader.md)
