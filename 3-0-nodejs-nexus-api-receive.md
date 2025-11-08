# Nexus API Receive (NodeJS Worker):
Here we set a sample NodeJS worker to listen to nexus api in command `samplecmd`:

```tsx
import { App } from './libs/bridge';

(async () => {

    console.clear()
    await App.Init(false); //init worker no rest api needed.
    await App.initUDB(); //optional
    await App.Connect({public:true}) //connect the worker

    App.on("samplecmd", async (specs) => {
        return { code: 0, myvalue:"Hi from NodeJS worker!" }
    })

})();

```
