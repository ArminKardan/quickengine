### `FAtoENRatio` Function

The `FAtoENRatio` function is used to evaluate the ratio of **Farsi (Persian)** characters to **non-Farsi** characters in a given string. This function is helpful for content validation, localization checks, and dynamic language-based rendering.

#### Import Statement

```ts
import { FAtoENRatio } from '@/frontend/components/qecomps/Cap';
```

---

### Description

**Function Signature**:
```ts
FAtoENRatio(input: string): number
```

- **Input**: A `string` to be evaluated.
- **Output**: A `number` between `0` and `1` representing the proportion of Farsi characters:
  - `1.0` → The string is fully Persian.
  - `0.0` → No Persian letters are present.

---

### Example

In this example, a string is sent from the back-end to the front-end. The `FAtoENRatio` function is used on the front-end to calculate the proportion of Farsi characters before rendering the result.

```ts
import { FAtoENRatio } from '@/frontend/components/qecomps/Cap';
import Component, { PageEl } from '@/frontend/components/qecomps/Component';
import type { GetServerSideProps, GetServerSidePropsContext } from 'next';

export default p => Component(p, Page);

const Page: PageEl = (props, refresh, getProps, onLoad, onConnected, dies, isFront, z) => {
  getProps(async (isFront) => {
    if (isFront) {
      props.ratio = FAtoENRatio(props.mystring);
    }
  });

  return (
    <div style={{ direction: z.lang.dir, padding: 10 }}>
      Ratio of mystring that received from backend is {props.ratio}
    </div>
  );
};
```

**Expected Output**:
If the string is `"hi من آرمینم"`, the function would return approximately `0.8`.

---

### Back-End Example (`getServerSideProps`)

```ts
export const getServerSideProps: GetServerSideProps = async (context: GetServerSidePropsContext) => {
  (global.Startup != "OK") ? (await (await import('@/startup.ts')).Starter()) : null;

  var session = await global.SSRVerify(context);
  var { lang, path, pageid } = session;

  let keys = ["region", "dir", "ff", "ffb", "support", "code", "textw", "txtmt"];
  let nlangs = {};
  for (let l of Object.keys(global.langs[lang])) {
    if (keys.includes(l)) nlangs[l] = global.langs[lang][l];
  }

  let obj = await Prosper({
    props: {
      mystring: "hi من آرمینم",
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

This allows developers to perform intelligent UI decisions based on the language content within strings.

---