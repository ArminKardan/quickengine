# Uploading Content to CDN via NodeJS Worker

In the QE ecosystem, the [NodeJS Worker](https://qepal.com/docs/3-0-nodejs) provides a convenient method to upload files or text to a content delivery network (CDN) using the `App.uploader()` method. This is useful for sharing files or storing logs and generated content.


## Example 1: Upload Text to CDN

You can upload any text content using `App.uploader`. Below is a complete example that uploads a plain text message to the CDN for 1 hour:

```ts
import { App } from './libs/bridge';

(async () => {

    console.clear()
    await App.Init(false); //run worker, no rest api needed.
    await App.initUDB(); //optional, initializing database
    await App.Connect({public:true}) //connect to nexus

    
    await App.uploader("Hello, this is test content.", 3600, "txt")

})();


```

### Parameters for `App.uploader`:

```ts
App.uploader(content, lifetime_in_seconds, extension)
```

- `content`: The content to be uploaded. This can be text or binary data.
- `lifetime_in_seconds`: The duration (in seconds) for which the file will remain on the server. Set to `0` to make it permanent.
- `extension`: File extension (e.g., `"txt"`, `"jpg"`, `"log"`), which defines the content type on upload.

---

## Example 2: Upload an Image to CDN

You can also upload binary files like images. Here’s how to upload a JPEG image:

```ts
import { App } from './libs/bridge';
import fs from 'fs';

(async () => {

    console.clear()
    await App.Init(false); //run worker, no rest api needed.
    await App.initUDB(); //optional, initializing database
    await App.Connect({public:true}) //connect to nexus

    let file = fs.readFileSync("./1.jpg")
    await App.uploader(file, 300, "jpg")

})();

```

This will upload the image for 5 minutes (300 seconds). After that, it will automatically be removed by the server.

---

## Notes

- `App.uploader` is fully integrated with QE's file system and CDN infrastructure.
- It's compatible with both text and binary content.
- All uploaded files will be accessible through a public CDN URL.