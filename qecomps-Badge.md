### `Badge` Component

The `Badge` component is a **Next.js** component used to display a small badge (15x15 pixels) as a visual indicator. It is styled with `inline-block` display and `vertical-align: middle`.

This component is useful for indicating roles or verification statuses in the UI. It accepts a single required prop:

#### Props

- **`verify`** (`string | null`):  
  Determines the appearance of the badge:
  - If `verify` is `'admin'` or `'owner'`:  
    - Badge color: **purple**
  - If `verify` is any other **non-empty string**:  
    - Badge color: **blue**
  - If `verify` is `null` or an **empty string**:  
    - **Badge is hidden** (not rendered)

#### Import Statement

```ts
import Badge from '@/frontend/components/qecomps/Badge';
```

---

### Example

The following example demonstrates different uses of the `Badge` component with various `verify` values:

```ts
import Badge from '@/frontend/components/qecomps/Badge';
import Component, { PageEl } from '@/frontend/components/qecomps/Component';

export default p => Component(p, Page);

const Page: PageEl = (props, refresh, getProps, onLoad, onConnected, dies, isFront, z) => {
  return (
    <div style={{ direction: z.lang.dir, padding: 10 }}>
      <Badge verify='admin' />       {/* Purple badge (15x15) */}
      <Badge verify='owner' />       {/* Purple badge (15x15) */}
      <Badge verify='moderator' />   {/* Blue badge (15x15) */}
      <Badge verify='' />            {/* No badge displayed */}
    </div>
  );
};
```

This behavior allows the UI to reflect different user statuses dynamically, improving clarity and visual feedback.

---