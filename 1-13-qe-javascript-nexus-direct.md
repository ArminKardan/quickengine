# QE Nexus Integration (Javascript)

## Overview

In QE Javascript environments (`microservice`, `xwebsite` frontend  and backend, GAPI), and also `nodejs-worker` the global `nexus` object enables communication with all blocks. This integration allows javascript applications to interact together using nexus.

## Nexus Direct

To interact with a Nexus worker, you must know the **Explore app name** (i.e., the name of the project to which the worker belongs).

### Basic Usage

```js
let response = await nexus.direct(specs)
```

### `specs` Format

The `specs` parameter is a JavaScript object with the following structure:

```ts
{
  app: string,               // (required) Explore app name
  body?: string,                // (optional) Payload data
  onlymine?: boolean,        // (optional) Target only my workers
  onlyowner?: boolean,       // (optional) Target only owner's workers
  prioritize_mine?: boolean, // (optional) Prefer my workers first
  resource?: string,         // (optional) Specific worker resource name
  jid?: string,              // (optional) Specific worker Jabber ID
}
```

### Field Descriptions

- **`app`**: *(string, required)*  
  The name of the Explore project to which the target worker belongs.

- **`body`**: *(any, optional)*  
  Payload object passed to the worker.

- **`resource`**: *(string, optional)*  
  Target a specific worker by resource name.

- **`onlymine`**: *(boolean, optional)*  
  If true, targets only workers created by the current front-end user (`uid`).

- **`onlyowner`**: *(boolean, optional)*  
  If true, targets only workers owned by the Explore project owner (`topuser`).

- **`prioritize_mine`**: *(boolean, optional)*  
  If true, prefers the current user's workers first; falls back to others if none found.

- **`jid`**: *(string, optional)*  
  Target a worker by its specific Jabber ID (JID).

> ⚠️ **Important:**  
> Communication with Nexus must always use the `nexus` object. Non-QE XMPP methods are not supported.

## Example

```ts
  let response = await nexus.direct({
    app: "etest",
    body: "hi"
  });

  if (response.code === 0) {
    alerter(response.result);
  }
```

## Example with `resource`

```jsx
  let response = await nexus.direct({
    app: "etest",
    resource:"default", //worker-nodejs with 'default' resource
    body: "hi"
  });

  if (response.code === 0) {
    alerter(response.result);
  }
```

## Example Get Message (only on nodejs worker)


### 🔹 Step 1: Assign Message Receiver

Define a handler for all incoming Nexus messages, including both **direct** and **channel-based** messages:

```js
nexus.msgreceiver = async (specs) => {
  // handle incoming message
}
```

### 🔹 Step 2: Send message

```jsx
  let response = await nexus.direct({
    app: "etest",
    resource:"default", //worker-nodejs with 'default' resource
    body: "hi"
  });

  if (response.code === 0) {
    console.log(response.result); //server side nodejs environment
    alerter(response.result); //on browser
  }
```

