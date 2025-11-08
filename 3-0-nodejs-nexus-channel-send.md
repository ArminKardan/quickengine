# Send data using Nexus Channel to a sample channel:

Here we send an direct request to `eagents` from a [NodeJS Worker](https://qepal.com/docs/4-worker-nodejs.md) block.

```ts
import { App } from './libs/bridge';

(async () => {

    console.clear()
    await App.Init(false); //run worker, no rest api needed.
    await App.initUDB(); //optional, initializing database
    await App.Connect({public:true}) //connect to nexus

    await nexus.subscribe("mychannel")
    await nexus.sendtochannel("mychannel", {myval:"Hi from NodeJS Worker!"})

})();


```

> Note that body only can be a javascript Object and inside it can be only JSON supported types.

