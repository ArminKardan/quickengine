# Send Nexus API request to a built-in QE app from NodeJS worker:
Here we send an api ping request to `eagents` from front-end of a [NodeJS Worker](https://qepal.com/docs/4-worker-nodejs.md) block.

```ts
import { App } from './libs/bridge';

(async () => {

    console.clear()
    await App.Init(false); //run worker, no rest api needed.
    await App.initUDB(); //optional, initializing database
    await App.Connect({public:true}) //connect to nexus

    let json = await nexus.api({app:"eagents", cmd:"ping"})
    console.log(json)

})();
```



# Send Nexus API request + Data to a built-in QE app from NodeJS worker:
Here we send an api ping request to `eagents` from front-end of a [NodeJS Worker](https://qepal.com/docs/4-worker-nodejs.md) block.

```ts
import { App } from './libs/bridge';

(async () => {

    console.clear()
    await App.Init(false); //run worker, no rest api needed.
    await App.initUDB(); //optional, initializing database
    await App.Connect({public:true}) //connect to nexus

    let json = await nexus.api({app:"eagents", cmd:"ping", body:{myval:"Hi from NodeJS Worker!"} })
    console.log(json)

})();
```

> Note that body only can be a javascript Object and inside it can be only JSON supported types.