# Nexus Direct Receive (NodeJS Worker):
Here we set a sample NodeJS worker to listen to directs:

```tsx
import { App } from './libs/bridge';

(async () => {

    console.clear()
    await App.Init(false); //run worker, no rest api needed.
    await App.initUDB(); //optional, initializing database
    await App.Connect({public:true}) //connect to nexus

    nexus.on.direct(async (specs)=>{
        let {app, body, fromjid, itsbro, itsme, resource, role, uid} = specs;
        console.log(specs)
    })
})();


```

> Note that body only can be a javascript Object and inside it can be only JSON supported types.
