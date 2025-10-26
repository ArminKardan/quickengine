
**`OpeningTitle` and `OpeningDetail`**:
By these two components we can have a customized drop-down components the `OpeningTitle` component will hold the title component and `OpeningDetail` will hold the content. they will be connect together by common `name` attribute At the first the `OpeningDetail` children is hidden and after clicking on `OpeningTitle` the `OpeningDetail`'s children will be shown. they can be imported by `import  OpeningTitle  from  '@/frontend/components/qecomps/OpeningTitle';` and `import  OpeningDetail  from  '@/frontend/components/qecomps/OpeningDetail';`

**Example 1:** Here we have an example. in our example we have a `Icon3Titles` as `OpeningTitle` and a paragraph as `OpeningDetail` they are connected to each other by `name='test'`:

```jsx
export default p => Component(p, Page);
const Page: PageEl = (props, refresh, getProps, onLoad, onConnected, dies, isFront, z) => {
  return <div style={{ direction: z.lang.dir, padding: 10 }}>
    <OpeningTitle name='test' onflip={(o) => { props.opendetail = o; refresh() }}>
      <Icon3Titles
        title1={"An opening item"}
        title2={<f-12 style={{ marginTop: 5 }}>Sedondary title</f-12>}
        title3={<f-12 style={{ marginTop: 5 }}>Tertiary title</f-12>}
        icon={cdn("/files/app/accountmngr.webp")}
        roundicon
        style={{ backgroundColor: "#B2C0D2", minHeight: 75 }}
        special={"special"}
        specialcolor={"green"} />
    </OpeningTitle>

    <OpeningDetail open={props.opendetail} name='test' >
      <p style={{ backgroundColor: "#80B07D" }}>{`the paragraph texts`}</p>
    </OpeningDetail>
  </div>
}
```

**Example 2:** Here we have a `OpeningTitle`-`OpeningDetail` pair that `OpeningDetail` is open by default and it shows the content of `OpeningDetail` but when user clicks on `OpeningTitle` the connected `OpeningDetail` will hide it's content. we use `getProps` function to set the `props.opendetail`'s value `true` before loading the page.

```jsx
export default p => Component(p, Page);
const Page: PageEl = (props, refresh, getProps, onLoad, onConnected, dies, isFront, z) => {
  getProps(async ()=>{
    props.opendetail = true
  })
  return <div style={{ direction: z.lang.dir, padding: 10 }}>
    <OpeningTitle name='test' onflip={(o) => { props.opendetail = o; refresh() }}>
      <Icon3Titles
        title1={"An opening item"}
        title2={<f-12 style={{ marginTop: 5 }}>Sedondary title</f-12>}
        title3={<f-12 style={{ marginTop: 5 }}>Tertiary title</f-12>}
        icon={cdn("/files/app/accountmngr.webp")}
        roundicon
        style={{ backgroundColor: "#B2C0D2", minHeight: 75 }}
        special={"special"}
        specialcolor={"green"} />
    </OpeningTitle>

    <OpeningDetail open={props.opendetail} name='test' >
      <p style={{ backgroundColor: "#80B07D" }}>{`the paragraph texts`}</p>
    </OpeningDetail>

  </div>
}
```

**Example 4:** In below example we have two different `OpeningTitle` and `OpeningDetail` pairs and each of them are connected using two different `name` values (One pair `name` is `testpair1` and the other is `testpair2`) and for one of them we use `Icon3Titles` as `OpeningTitle` and in the other we used `Icon2Titles` and the first pair is open by default:

```jsx
export default p => Component(p, Page);
const Page: PageEl = (props, refresh, getProps, onLoad, onConnected, dies, isFront, z) => {
  getProps(async ()=>{
    props.opendetail1 = true
  })
  return <div style={{ direction: z.lang.dir, padding: 10 }}>
    <OpeningTitle name={"testpair1"} onflip={(o) => { props.opendetail1 = o; refresh() }}>
      <Icon3Titles
        title1={"An opening item"}
        title2={<f-12 style={{ marginTop: 5 }}>Sedondary title</f-12>}
        title3={<f-12 style={{ marginTop: 5 }}>Tertiary title</f-12>}
        icon={cdn("/files/app/accountmngr.webp")}
        roundicon
        style={{ backgroundColor: "#B2C0D2", minHeight: 75 }}
        special={"special"}
        specialcolor={"green"} />
    </OpeningTitle>

    <OpeningDetail open={props.opendetail1}   name={"testpair1"}  >
      <p style={{ backgroundColor: "#80B07D" }}>{`the paragraph texts`}</p>
    </OpeningDetail>

    <br-x/>

    <OpeningTitle name={"testpair2"} onflip={(o) => { props.opendetail2 = o; refresh() }}>
      <Icon2Titles
        title1={"An opening item"}
        title2={<f-12 style={{ marginTop: 5 }}>Sedondary title</f-12>}
        icon={cdn("/files/app/accountmngr.webp")}
        roundicon
        style={{ backgroundColor: "#B2C0D2", minHeight: 75 }}
        />
    </OpeningTitle>
    <OpeningDetail name={"testpair2"}  open={props.opendetail2} >
      <p style={{ backgroundColor: "#80B07D" }}>{`the paragraph texts`}</p>
    </OpeningDetail> 
  </div>
}
```
