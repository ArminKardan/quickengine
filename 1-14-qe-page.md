# QE Page Structure

In QE, both `microservice` and `xwebsite` projects support multilingual page rendering and user-aware session handling. Each page is built using a unified structure with front-end and back-end components.

---

## 📁 Page File Location

Each language-specific page is located at:

```
./pages/[lang]/index.tsx
```

- `[lang]` represents the selected language of the user:
  - For `microservice`, it's the `middleuser`'s language.
  - For `xwebsite`, it's the `enduser`'s language.

---

## 🧱 Minimum Page Template

Below is the **minimum boilerplate** to define a valid QE page:

```tsx
import Component, { PageEl } from '@/frontend/components/qecomps/Component'
import type { GetServerSideProps, GetServerSidePropsContext } from 'next'

// Frontend rendering function:
export default p => Component(p, Page)

const Page: PageEl = (
  props,
  refresh,
  getProps,
  onLoad,
  onConnected,
  dies,
  isFront,
  z
) => {
  return <div style={{ direction: z.lang.dir, padding: 10 }}></div>
}

// Backend rendering logic:
export const getServerSideProps: GetServerSideProps = async (context: GetServerSidePropsContext) => {

  (global.Startup != "OK") ? (await (await import('@/startup.ts')).Starter()) : null

  var session = await global.SSRVerify(context, false, [])
  var { lang, path, pageid, nlangs } = session;


  // Perform any additional backend logic here (GAPI, Nexus, Database, Global functions etc)

  let obj = await Prosper({
    props: {
      
      //add any values here to receive them on props on front end.

      query: context.query,
      nlangs,
      path,
      session,
      title: "test title", //the page's title
      description: "test description", // the page's description
      pageid,
    },
  }, context)

  return obj
}
```

---

## 🔍 Notes

- `Component(p, Page)` is a QE wrapper that ensures proper lifecycle and context binding.
- The `Page` function supports automatic props and lifecycle injection (`onLoad`, `onConnected`, `dies`, etc.).
- The server-side `getServerSideProps` integrates:
  - Language resolution
  - Session verification
  - Metadata injection (`title`, `description`)
  - Translation keys injection from global context (`global.langs`)
