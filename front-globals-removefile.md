# `removefile`

The `removefile` function is a global front-end utility used to remove a file URL from the server. This action can only be performed from a front-end where the user is authenticated.


```jsx
await removefile(url: string)
```

## Example

```jsx
<b-200 class="btn btn-info" onClick={async () => {
  await removefile("https://cdn.qepal.com/qeupload/635111b8ff61db2b04928f49/7hxec0clhxxx2eoxqu8c99.jpg");
}}>Remove a url from server</b-200>
```

If the operation is successful, the file will be removed from the server. This function requires the user to be logged in.