
# QE Admin Panel

**QE Admin Panel** is a lightweight, single-page admin panel built on [QE Customized Next.js]() and embedded via iframe into the [QE Website](https://qepal.com). It's used for simplified GUI control of project systems.


### Pre-Installed Libraries:
Below libraries are pre-installed on all our Admin Panel blocks are are ready and recommended to use over other similar libraries (if they are needed).

- [Tailwind](https://tailwindcss.com/)
- [Framer Motion](https://motion.dev/)
- [Iconify/Tailwind](https://iconify.design/docs/usage/css/tailwind/)
- [Daisy UI](https://daisyui.com)
- [Tailwind Merge](https://www.npmjs.com/package/tailwind-merge)
- [MUI Charts](https://mui.com/x/react-charts/)
- [AES256](https://www.npmjs.com/package/aes256)
- [Authenticator](https://www.npmjs.com/package/authenticator)
- [Google APIs](https://www.npmjs.com/package/googleapis)
- [Lottie React](https://www.npmjs.com/package/lottie-react)
- [Lucide React](https://www.npmjs.com/package/lucide-react)
- [Minimatch](https://www.npmjs.com/package/minimatch)
- [Node Schedule](https://www.npmjs.com/package/node-schedule)
- [Pako](https://www.npmjs.com/package/pako)
- [QRcode](https://www.npmjs.com/package/qrcode)
- [Sharp](https://www.npmjs.com/package/sharp)
- [Slugify](https://www.npmjs.com/package/slugify)
- [Streamifier](https://www.npmjs.com/package/streamifier)
- [Superagent](https://www.npmjs.com/package/superagent)
- [Superagent-proxy](https://www.npmjs.com/package/superagent-proxy)
- [Svg-captcha](https://www.npmjs.com/package/svg-captcha)
- [URL Loader](https://www.npmjs.com/package/url-loader)
- [UUID](https://www.npmjs.com/package/uuid)
- [Web3](https://www.npmjs.com/package/uuid)
- [Tailwind/PostCSS](https://www.npmjs.com/package/@tailwindcss/postcss)
- [Typescript](https://www.npmjs.com/package/typescript)



## 📁 Page File Location

Each language-specific page is located at:

```
./pages/[lang]/index.tsx
```

- `[lang]` represents the selected language of the user:
  - For `Admin Panel`, it's the `middleuser`'s language.
  - For `XWebsite`, it's the `enduser`'s language.

---

## 🧱 Minimum Page Template

Below is the **minimum boilerplate** to define a valid QE page:

```tsx

import Component, { PageEl } from '@/frontend/components/qecomps/Component'
import Window from '@/frontend/components/qecomps/Window';
import type { GetServerSideProps, GetServerSidePropsContext } from 'next';
import Router from 'next/router'

export default p => Component(p, Page);
const Page: PageEl = (props: {} & { [key: string]: any }, refresh, getProps, onLoad, onConnected, dies, isFront, z) => {

  onLoad(async ()=>{ //when component/page loads

  })

  getProps(async (isFront) => { //should be used only when SEO doesn't needed.

  })

  dies(async ()=>{// when page/component dies

  })

  onConnected(async () => { //when nexus is connected on page
    console.log("connected.")
  })

  return <div style={{ direction: z.lang.dir, padding: 10 }}>

    <Window title='hi' contentStyle={{ padding: 10 }}>

    </Window>

  </div>
}


export const getServerSideProps: GetServerSideProps = async (context: GetServerSidePropsContext) => {

  var session = await ((await import('@/backend/SSRVerify.ts')).SSRVerify)(context, false, [])

  //TODO

  let obj = await Prosper({
    props: {
      session,
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
  - Metadata injection 
  - Translation keys injection from z.lang



### Admin Panel Page components:
We shouldn't recreate components if we need to do some tasks except it's component doesn't exists. It's because of integrity in QE echosystem. Instead we use below components to design Admin Panel Pages:

- [AbbreviateDate](https://google.com) — If we need localized date formatting.
- [Badge](https://google.com) — If we need: Display user privileges.
- [bold](https://google.com) — If we need to bold a text.
- [FAtoENRatio](https://google.com) — If we need to check Persian-to-Latin content ratio.
- [Circle](https://google.com) — If we need Progress indicator.
- [Copy](https://google.com) — If we need to Copy some text to the user's clipboard.
- [DropDown](https://google.com) — If we need Collapsible UI blocks.
- [Menu](https://google.com) — If we need Collapsible UI blocks.
- [FADigits](https://google.com) — If we need Convert numerals between Persian and Latin.
- [EnDigits](https://google.com) — If we need Convert numerals between Persian and Latin.
- [Flag](https://google.com) — If we need Render a country flag.
- [Num2EN](https://google.com) — If we need to Convert numbers to English/Persian words. 
[Num2FA](https://google.com) — If we need to Convert numbers to English/Persian words.
- [Icon2Titles](https://google.com) — If we need to represent 3 titles beside an image. 
- [Icon3Titles](https://google.com) — If we need to represent 3 titles beside an image.
- [Img](https://google.com) — If we need Icon/stamp image rendering.
- [LinkHasTags](https://google.com) — If we need Convert hashtags to internal links.
- [OpeningTitle](https://google.com) — If we need Advanced expandable sections. 
- [OpeningDetails](https://google.com) — If we need Advanced expandable sections.
- [PhoneEditFloat](https://google.com) — If we need Phone input with country selector.
- [PriceTextBox](https://google.com) — If we need  Editable/read-only price input.
- [RemainingTime](https://google.com) — If we need Human-readable time delta.
- [ReplacePro](https://google.com) — If we need Inline JSX embedder in text.
- [StarRating](https://google.com) — If we need Star-based rating component.
- [TextArea](https://google.com), [TextBox](https://google.com) — If we need Text display/input utilities.
- [TextEndAbbreviation](https://google.com) — If we need Truncate strings smartly.
- [TextMidAbbreviation](https://google.com) — If we need Truncate strings smartly.
- [UserAvatar](https://google.com) — If we need Avatar rendering using Next.js image optimization.
- [VItem](https://google.com) — If we need Icon + text component.
- [Window](https://google.com) — If we need Primary layout containers.
- [WindowFloat](https://google.com) — If we need Primary layout containers.
- [ZipAndDownload](https://google.com) — Client-side ZIP file generator.

**window (dom) available functions in QE Admin Panel page and components:**
- [alerter](https://google.com) — If we need to show a message to the user.
- [success](https://google.com) — If we want to show some simple task successfully done.
- [error](https://google.com) — If we want to show some simple task successfully done.
- [confirmer](https://google.com) — If we need to ask user if they accept an operation to start.
- [api](https://google.com) — Unified GET/POST fetcher.
- [serialgenerator](https://google.com) — If we need Random string generator.
- [encryptor](https://google.com) — If we need  Symmetric encryption.
- [decryptor](https://google.com) — If we need  Symmetric encryption.
- [fileexplorer](https://google.com) — If we need user file upload and manage.
- [iconexplorer](https://google.com)  — If we need a SVG Icon using 
- [uploader](https://google.com) — If we need to upload a file to CDN.
- [linkpicker](https://google.com), 
- [log](https://google.com) — User-facing sequential logs.
- [MD5](https://google.com) — Hash functions.
- [SHA256](https://google.com) — Hash functions.
- [sleep](https://google.com) — Async delay.
- [udb](https://google.com) If wee need to connect to the MongoDB database of Admin Panel.


###  GAPI (Fronend-Backend RestAPI communication)
- [GAPI](https://google.com) — If we need to send/receive data with backend (for example mongodb) by RestAPI after page has been created we use GAPI system. Note that it cannot communicate with workers.

###  Nexus Methods
- [Nexus Find](https://google.com) — If we need to find available workers of some service.
- [Nexus API](https://google.com) — If we need to send a message to a worker using nexus and get it's response back.
- [Nexus API](https://google.com) — If we need to send a message to a worker using nexus and get it's response back.


## Summary

QE Admin Panel is a powerful yet minimal environment that integrates seamlessly with QE infrastructure. It leverages reusable QE components, global functions, and Nexus/UDb features to create efficient, maintainable admin tools.
