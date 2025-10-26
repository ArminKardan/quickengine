## `UserAvatar`

The `UserAvatar` component displays a **circular user avatar image**, using Next.js's `<Image>` component for optimized image loading and compression.

### Import Path

```ts
import UserAvatar from '@/frontend/components/qecomps/UserAvatar';
```

### Notes

Make sure to configure your `next.config.mjs` properly to allow the required image domains. A sample configuration:

```js
images: {
  minimumCacheTTL: 360000,
  domains: [
    process.env.DOMAIN,
    "cdn.qepal.com",
    "*.githubusercontent.com",
    "avatars.githubusercontent.com",
    "raw.githubusercontent.com",
    "gravatar.com",
    "qepal.com",
    "lh3.googleusercontent.com",
  ],
}
```

### Props

- `image` (string): URL of the user's avatar image.
- `width` (number): The width of the avatar in pixels (height will match to maintain circular shape).

### Example

```jsx
<UserAvatar image={z.middleuser.image} width={35} />
```

This renders the current `middleuser`'s avatar at a size of `35px` by `35px`.