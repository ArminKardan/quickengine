

# QE Nexus Integration (Javascript)

## Overview

Here we are explaining how to send Nexus API requests to the workers and how to make an Nexus API listener on a `nodejs-worker`.


## Nexus API / Send Request


To interact with a Nexus worker, you must know the **Explore app name** (i.e., the name of the project to which the worker belongs). 
> Sending Nexus API has common method in all QE Javascript environments (`microservice`, `xwebsite` frontend and backend) and `nodejs-worker`.



### ⚙️ Function Signature

```ts
let response = await nexus.api({
  app: string,               // (required) Explore app name
  cmd: string,               // (required) Worker listener command
  body?: any,                // (optional) Payload data
  onlymine?: boolean,        // (optional) Target only my workers
  onlyowner?: boolean,       // (optional) Target only owner's workers
  prioritize_mine?: boolean, // (optional) Prefer my workers first
  resource?: string,         // (optional) Specific worker resource name
  jid?: string,              // (optional) Specific worker Jabber ID
})
```


### Field Descriptions

- **`app`**: *(string, required)*  
  The name of the Explore project to which the target worker belongs.

- **`cmd`**: *(string, required)*  
  The command or listener function name in the worker.

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

```jsx

  let response = await nexus.api({
    app: "etest",
    cmd: "multiply",
    body: { num1: 10, num2: 5 }
  });

  if (response.code === 0) {
    console.log(response.result); //nodejs environments
    alerter(response.result); //on browser
  }
```

