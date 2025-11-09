# Find Nexus Workers

In the example below we find all workers that is available from a Service named `emyapp` and send a `ping` by [Nexus API](https://qepal.com/docs/3-0-nodejs-nexus-api-send.md) to it.


```ts
import { App } from './libs/bridge';

(async () => {

    console.clear()
    await App.Init(false); //run worker, no rest api needed.
    await App.initUDB(); //optional, initializing database
    await App.Connect({public:true}) //connect to nexus

    let json = await nexus.find({app:"emyapp"});
    if(json.code == 0 && json.jids.length > 0)
    {
      let jid = json.jids.at(0);
      let json_api = await nexus.api({app:"emyapp", cmd:"ping", jid })
      console.log(json_api)
    }
    
})();
```

