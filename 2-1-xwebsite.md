
# QE XWebsite

**XWebsite** is a customizable multi-page website (based on Customized-Next.js), typically hosted on a subdomain of [QE Website](https://qepal.com) or a custom domain. It's designed for end-user interaction—especially those unfamiliar with QE—while depending on QE only for back-end infrastructure.

### Pre-Installed Libraries:
Below libraries are pre-installed on all our XWebsite blocks are are ready and recommended to use over other similar libraries (if they are needed).
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



### Server-side Features (Page Backend & GAPI)
- Access to both [udb](https://qepal.com/docs/1-15-qe-nodejs-udb.md) (Universal DB) and [xdb](https://qepal.com/docs/1-15-qe-xwebsite-xdb.md) (User DB)
- Supports `Nexus-API Send`, `Nexus-Direct Send`, `Nexus-Channel Send`
- Frontend supports: `Nexus-API Send`, `Nexus-Direct Send`, `Nexus-Channel Send`, `Nexus-Channel Receive`

### Frontend Capabilities
Supports all QE Components, custom tags, and global functions, including login and user-profile functions.

---

### XWebsite Page components:
We shouldn't recreate components if we need to do some tasks except it's component doesn't exists. It's because of integrity in QE echosystem. Instead we use below components to design XWebsite Pages:

These are reusable UI utilities designed to reduce redundancy and provide consistent UX:



- [AbbreviateDate](https://qepal.com/docs/qecomps-AbbreviateDate.md) — If we need localized date formatting.
- [Badge](https://qepal.com/docs/qecomps-Bold.md) — If we need: Display user privileges.
- [Bold](https://qepal.com/docs/qecomps-Bold.md) — If we need to bold a text.
- [FAtoENRatio](https://qepal.com/docs/qecomps-FAtoENRatio.md) — If we need to check Persian-to-Latin content ratio.
- [Circle](https://qepal.com/docs/qecomps-Circle.md) — If we need Progress indicator.
- [Copy](https://qepal.com/docs/qecomps-Copy.md) — If we need to Copy some text to the user's clipboard.
- [DropDown](https://qepal.com/docs/qecomps-DropDown.md) — If we need Collapsible UI blocks.
- [Menu](https://qepal.com/docs/qecomps-Menu.md) — If we need Collapsible UI blocks.
- [FADigits](https://qepal.com/docs/qecomps-FaDigits.md) — If we need Convert numerals between Persian and Latin.
- [EnDigits](https://qepal.com/docs/qe-qecomps-EnDigits.md) — If we need Convert numerals between Persian and Latin.
- [Flag](https://qepal.com/docs/qecomps-Flag.md) — If we need Render a country flag.
- [Num2EN](https://qepal.com/docs/qecomps-Num2EN.md) — If we need to Convert numbers to English/Persian words. 
- [Num2FA](https://qepal.com/docs/qecomps-Num2FA.md) — If we need to Convert numbers to English/Persian words.
- [Icon2Titles](https://qepal.com/docs/qecomps-Icon2Titles.md) — If we need to represent 3 titles beside an image. 
- [Icon3Titles](https://qepal.com/docs/qecomps-Icon3Titles.md) — If we need to represent 3 titles beside an image.
- [Img](https://qepal.com/docs/qecomps-Img.md) — If we need Icon/stamp image rendering.
- [LinkHasTags](https://qepal.com/docs/qecomps-LinkHashTags.md) — If we need Convert hashtags to internal links.
- [OpeningTitle](https://qepal.com/docs/qecomps-OpeningTitle-OpeningDetail.md) — If we need Advanced expandable sections. 
- [OpeningDetails](https://qepal.com/docs/qecomps-OpeningTitle-OpeningDetail.md) — If we need Advanced expandable sections.
- [PhoneEditFloat](https://qepal.com/docs/qecomps-PhoneEditFloat.md) — If we need Phone input with country selector.
- [PriceTextBox](https://qepal.com/docs/qecomps-PriceTextBox.md) — If we need  Editable/read-only price input.
- [RemainingTime](https://qepal.com/docs/qecomps-RemainingTime.md) — If we need Human-readable time delta.
- [ReplacePro](https://qepal.com/docs/qecomps-ReplacePro.md) — If we need Inline JSX embedder in text.
- [StarRating](https://qepal.com/docs/qecomps-StarRating.md) — If we need Star-based rating component.
- [TextArea](https://qepal.com/docs/qecomps-TextArea.md) — If we need Text display/input utilities.
- [TextBox](https://qepal.com/docs/qecomps-TextBox.md) — If we need Text display/input utilities.
- [TextEndAbbreviation](https://qepal.com/docs/qecomps-TextEndAbbreviation.md) — If we need Truncate strings smartly.
- [TextMidAbbreviation](https://qepal.com/docs/qecomps-TextMidAbbreviation.md) — If we need Truncate strings smartly.
- [UserAvatar](https://qepal.com/docs/qecomps-UserAvatar.md) — If we need Avatar rendering using Next.js image optimization.
- [VItem](https://qepal.com/docs/qecomps-VItem.md) — If we need Icon + text component.
- [Window](https://qepal.com/docs/qecomps-Window.md) — If we need Primary layout containers.
- [WindowFloat](https://qepal.com/docs/qecomps-WindowFloat.md) — If we need Primary layout containers.
- [ZipAndDownload](https://qepal.com/docs/qecomps-ZipAndDownload.md) — Client-side ZIP file generator.
---

**window (dom) available functions in QE XWebsite page and components:**
- [alerter](https://qepal.com/docs/front-globals-alerter.md) — If we need to show a message to the user.
- [success](front-globals-success.md) — If we want to show some simple task successfully done.
- [error](https://qepal.com/docs/front-globals-error.md) — If we want to show some simple task successfully done.
- [confirmer](https://qepal.com/docs/front-globals-confirmer.md) — If we need to ask user if they accept an operation to start.
- [api](https://qepal.com/docs/back-globals-api.md) — Unified GET/POST fetcher.
- [serialgenerator](https://qepal.com/docs/javascript-globals-serialgenerator.md) — If we need Random string generator.
- [encryptor](https://qepal.com/docs/javascript-globals-encryptdecrypt.md) — If we need  Symmetric encryption.
- [decryptor](https://qepal.com/docs/javascript-globals-encryptdecrypt.md) — If we need  Symmetric encryption.
- [fileexplorer](https://qepal.com/docs/front-globals-fileexplorer.md) — If we need user file upload and manage.
- [iconexplorer](https://qepal.com/docs/front-globals-iconexplorer.md)  — If we need a SVG Icon using 
- [uploader](https://qepal.com/docs/javascript-globals-uploader.md) — If we need to upload a file to CDN.
- [linkpicker](https://qepal.com/docs/front-globals-linkpicker.md) — If we need to upload a file to CDN or select from previous links or set a link directly by textbox.
- [log](https://qepal.com/docs/front-globals-log.md) — User-facing sequential logs.
- [MD5](https://qepal.com/docs/javascript-globals-md5.md) — Hash functions.
- [SHA256](https://qepal.com/docs/javascript-globals-sha256.md) — Hash functions.
- [sleep](https://qepal.com/docs/javascript-globals-sleep.md) — Async delay.
- [udb](https://qepal.com/docs/1-15-qe-nodejs-udb.md) If wee need to connect to the MongoDB database of XWebsite (Available to [topuser](https://qepal.com/docs/1-15-qe-xwebsite-xdb.md).
- [xdb](https://qepal.com/docs/1-15-qe-xwebsite-xdb.md) If wee need to connect to the MongoDB database of XWebsite (Available to [topuser](https://qepal.com/docs/) and [middleuser](https://qepal.com/docs/)).

- [loginbyQE](https://qepal.com/docs/xfront-globals-loginbyqe.md) If we need enduser to login to XWebsite by QE Authentication.
- [loginbyGoogle](https://qepal.com/docs/xfront-globals-loginbygoogle.md) If we need enduser to login to XWebsite by Google Authentication.
- [loginbyLinkedIn](https://qepal.com/docs/xfront-globals-loginbylinkedin.md) If we need enduser to login to XWebsite by LinkedIn Authentication.
- [loginbyGitHub](https://qepal.com/docs/xfront-globals-loginbygithub.md) If we need enduser to login to XWebsite by GitHub Authentication.
- [loginbyphone](https://qepal.com/docs/xfront-globals-loginbyphone.md) If we need enduser to login to XWebsite by Phone Authentication (Only works in Persian language).
- [changeenduser.image](https://qepal.com/docs/xfront-globals-changeenduser-image.md) If We need to change enduser's Profile Image (Note: it will change enduser's image all accross QE Echosystem)
- [changeenduser.name](https://qepal.com/docs/xfront-globals-changeenduser-name.md) If We need to change enduser's Name (Note: it will change enduser's image all accross QE Echosystem)


it also has third party library installation capability from `npm` from QE Explore manager.
