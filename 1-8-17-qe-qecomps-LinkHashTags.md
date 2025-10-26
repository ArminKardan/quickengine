
## `LinkHashTags`

**`LinkHashTags`**: It's a function that returns elements and it will take a string and will convert every word that starts with single `#` and double hash (`##`) into a link based on its input options.

**Import Statement:**
```ts
import LinkHashtags from '@/frontend/components/qecomps/LinkHashtags';
```

**Example:** Here we have a text that we want the words that start with `#` or `##` to be links:

```jsx
export default p => Component(p, Page);
const Page: PageEl = (props, refresh, getProps, onLoad, onConnected, dies, isFront, z) => {
  return <div style={{ direction: z.lang.dir, padding: 10 }}>
    {LinkHashtags(\`Lorem ipsum dolor sit amet consectetur adipisicing elit. Doloribus, et 
           vero enim reprehenderit #AbbreviateDate veritatis ##AbbreviateDate, nostrum, vel commodi quasi 
           quaerat tenetur necessitatibus dolore illo harum. Harum dicta est tenetur?\`, "test",
      {
        ondouble: (tag) => { console.log(\`on double:\${tag}\`) },
        onsingle: (tag) => { console.log(\`on single:\${tag}\`) },
        singleprelink: z.root + "/link1/",
        doubleprelink: z.root + "/link2/",
      })}
  </div>
}
```

### Behavior:
- The output of the above example is a text with embedded links.
- If a word starts with `#`, such as `#AbbreviateDate`, it will be converted to a link pointing to:
  `/[userlang]/link1/AbbreviateDate`.
- For example, if the selected language is Persian, the link would be `/fa/link1/AbbreviateDate`.
- Clicking this link logs: `on single AbbreviateDate` to the console.
- If a word starts with `##`, such as `##AbbreviateDate`, it will link to:
  `/[userlang]/link2/AbbreviateDate` and log: `on double AbbreviateDate`.
