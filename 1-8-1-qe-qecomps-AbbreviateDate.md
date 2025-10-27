### `AbbreviateDate` Function

The `AbbreviateDate` function is a utility (not a Next.js component) used to format and abbreviate a given date based on the user's language and region settings. It is imported from:

```
@/frontend/components/qecomps/AbbreviateDate
```

#### Function Signature

```ts
AbbreviateDate(date: Date | number | string, z: ZType): string
```

- **`date`** (type: `Date | number | string`):  
  - If the input is a `number`, it must be in **Unix Timestamp** format.  
  - If the input is a `string`, it must follow the **ISO 8601** time format.  
  - `Date` objects are also accepted directly.

- **`z`** (type: `ZType`):  
  Represents user preferences including selected language and country-zone settings.

---

### Example 1

#### Goal:
Display a formatted and localized date (`2000/01/01 14:35`) according to the user's selected language and region.

#### Frontend Code (Admin Panel or XWebsite):

```ts
import AbbreviateDate from '@/frontend/components/qecomps/AbbreviateDate';
import Component, { PageEl } from '@/frontend/components/qecomps/Component';
import type { GetServerSideProps, GetServerSidePropsContext } from 'next';

export default p => Component(p, Page);

const Page: PageEl = (props, refresh, getProps, onLoad, onConnected, dies, isFront, z) => {
  return (
    <div style={{ direction: z.lang.dir, padding: 10 }}>
      {AbbreviateDate(new Date(2000, 0, 1, 14, 35, 0), z)}
    </div>
  );
};
```

If the user selects the **Persian** language, the region will automatically be set to `fa-IR`, and the output will be:

```
۱۳۷۸/۱۰/۱۱
```

#### Note:

In QE Pages (when the code belongs to a page rather than a standalone component), a minimal backend setup is required. Although backend logic is similar across examples and often omitted for brevity, here's a sample implementation:

```ts
export const getServerSideProps: GetServerSideProps = async (context: GetServerSidePropsContext) => {
  if (global.Startup !== "OK") {
    await (await import('@/startup.ts')).Starter();
  }

  const session = await global.SSRVerify(context);
  const { lang, path, pageid } = session;

  const keys = ["region", "dir", "ff", "ffb", "support", "code", "textw", "txtmt"];
  const nlangs: Record<string, any> = {};

  for (const key of Object.keys(global.langs[lang])) {
    if (keys.includes(key)) {
      nlangs[key] = global.langs[lang][key];
    }
  }

  const obj = await Prosper({
    props: {
      query: context.query,
      nlangs,
      path,
      session,
      title: "test title",
      description: "test description",
      pageid,
    },
  }, context);

  return obj;
};
```

---

### Example 2

#### Goal:
Format the Unix timestamp `1748154015` into a human-readable format according to the user's selected language.

#### Frontend Code:

```ts
import AbbreviateDate from '@/frontend/components/qecomps/AbbreviateDate';
import Component, { PageEl } from '@/frontend/components/qecomps/Component';
import type { GetServerSideProps, GetServerSidePropsContext } from 'next';

export default p => Component(p, Page);

const Page: PageEl = (props, refresh, getProps, onLoad, onConnected, dies, isFront, z) => {
  return (
    <div style={{ direction: z.lang.dir, padding: 10 }}>
      {AbbreviateDate(1748154015, z)}
    </div>
  );
};
```

---

### Example 3

#### Goal:
Format an ISO 8601 string (`2025-05-25T06:20:15.269Z`) into a user-friendly format based on the selected language.

#### Frontend Code:

```ts
import AbbreviateDate from '@/frontend/components/qecomps/AbbreviateDate';
import Component, { PageEl } from '@/frontend/components/qecomps/Component';
import type { GetServerSideProps, GetServerSidePropsContext } from 'next';

export default p => Component(p, Page);

const Page: PageEl = (props, refresh, getProps, onLoad, onConnected, dies, isFront, z) => {
  return (
    <div style={{ direction: z.lang.dir, padding: 10 }}>
      {AbbreviateDate('2025-05-25T06:20:15.269', z)}
    </div>
  );
};
```