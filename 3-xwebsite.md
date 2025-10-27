
# QE XWebsite

**XWebsite** is a customizable multi-page website (based on Customized-Next.js), typically hosted on a subdomain of [QE Website](https://qepal.com/docs/3-xwebsite) or a custom domain. It's designed for end-user interaction—especially those unfamiliar with QE—while depending on QE only for back-end infrastructure.

Note:

### Server-side Features (Page Backend & GAPI)
- Access to both `udb` (Universal DB) and `xdb` (User DB)
- Supports `Nexus-API Send`, `Nexus-Direct Send`, `Nexus-Channel Send`
- Frontend supports: `Nexus-API Send`, `Nexus-Direct Send`, `Nexus-Channel Send`, `Nexus-Channel Receive`

### Frontend Capabilities
Supports all QE Components, custom tags, and global functions, including login and user-profile functions.

---

### XWebsite Page components:
We shouldn't recreate components if we need to do some tasks except it's component doesn't exists. It's because of integrity in QE echosystem. Instead we use below components to design XWebsite Pages:

These are reusable UI utilities designed to reduce redundancy and provide consistent UX:


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
---

**window (dom) available functions in QE XWebsite page and components:**
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
- [MD5](https://google.com)  — If we need to Hash a string
- [SHA256](https://google.com) — If we need to Hash a string
- [udb](https://google.com) If wee need to connect to the MongoDB database of XWebsite (Available to [topuser](https://google.com)).
- [xdb](https://google.com) If wee need to connect to the MongoDB database of XWebsite (Available to [topuser](https://google.com) and [middleuser](https://google.com)).

- [loginbyQE](https://google.com) If we need enduser to login to XWebsite by QE Authentication.
- [loginbyGoogle](https://google.com) If we need enduser to login to XWebsite by Google Authentication.
- [loginbyLinkedIn](https://google.com) If we need enduser to login to XWebsite by LinkedIn Authentication.
- [loginbyGitHub](https://google.com) If we need enduser to login to XWebsite by GitHub Authentication.
- [loginbyphone](https://google.com) If we need enduser to login to XWebsite by Phone Authentication (Only works in Persian language).
- [changeenduser.image](https://google.com) If We need to change enduser's Profile Image (Note: it will change enduser's image all accross QE Echosystem)
- [changeenduser.name](https://google.com) If We need to change enduser's Name (Note: it will change enduser's image all accross QE Echosystem)
- [changeenduser.unit](https://google.com) If We need to change enduser's Monetary Unit (Note: it will change enduser's image all accross QE Echosystem)
- [changeenduser.lang](https://google.com) If We need to change enduser's Primary language (Note: it will change enduser's image all accross QE echosystem)



it also has third party library installation capability from `npm` from QE Explore manager.
