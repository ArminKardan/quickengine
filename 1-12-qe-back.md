## QE Page Microservice Backend

In QE front-end environments (`microservice` and `xwebsite`), we use the `getServerSideProps` function to implement the backend for pages. This function fetches required data before rendering the page.

### Basic Backend Setup

Here’s the minimum backend code to set up a page:

```ts
export const getServerSideProps: GetServerSideProps = async (context: GetServerSidePropsContext) => {
  // Start up if needed
  (global.Startup != "OK") ? (await (await import('@/startup.ts')).Starter()) : null;

  // Verify session
  var session = await global.SSRVerify(context, false, []);
  var { 
    app, 
    cat, 
    expid, 
    topuser, // Developer of the microservice
    middleuser, // User in the microservice
    lang, 
    path, 
    pageid, 
    nlangs, 
  } = session;

  // Additional backend logic (e.g., GAPI, Nexus, DB calls)

  // Return data to front-end
  let obj = await Prosper({
    props: {
      query: context.query,
      nlangs,
      path,
      session,
      title: "Test Title",
      description: "Test Description",
      pageid,
    },
  }, context);

  return obj;
};
```

### `session` Object

The `session` object contains vital information about the client:

```ts
session : {
  app: string,  // Explore app name
  cat: string,  // Explore category
  expid: ObjectId,  // Unique Explore ID
  topuser: TopUserType,  // Top user specifications
  middleuser: MiddleUserType,  // Middle user specifications
  lang: langType,  // Language type (2-character code)
  path: string,  // Current web path
  userip: string,  // Client's IP address
}
```

### `TopUserType`

Represents the top-level user (developer of the microservice):

```ts
TopUserType : {
  uid: ObjectId,  // Unique ID in QE
  name: string,
  image: string,
  ccode: string,  // Country code (+1, +98, +971,...)
  cchar: string,  // Country character (e.g., "us", "ir")
  phone: string,
  email: string,
  lang: langType,  // Language type ("fa", "en", "fr", etc.)
  unit: UnitName,  // Monetary unit ("usd", "toman", "aud", etc.)
}
```

### `MiddleUserType`

Represents the user of the microservice:

```ts
MiddleUserType : {
  name: string, 
  image: string,
  cchar: string,  // Country character (e.g., "us", "ir")
  unit: string,  // Monetary unit
  phone: string,
  email: string,
  ccode: string,  // Country code (+1, +98, +971,...)
  lang: string,  // Language type ("fa", "en", "fr")
  servid: ObjectId,  // Service unique ID
  mongourl: string,  // MongoDB URL
  uid: ObjectId,  // Unique ID in QE
  usedquota: number,  // Used quota
  quota: number,  // Max quota
  quotaunit: string,  // Unit of quota
  status: "approved" | "rejected" | "waiting",  // Service status
  regdate: number,  // Registration date
  servsecret: string,  // Service secret code
  role: Array<RoleName>,  // Roles assigned to the user
  rolecheck: (check: Array<RoleName>) => boolean,  // Role check function
  tempsecret: { 
    generate: () => Promise<string>,  // Generate MFA code
    verify: (input: string) => Promise<boolean>  // Verify MFA code
  },
}
```