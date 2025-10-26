
# QE XWebsite

**XWebsite** is a customizable multi-page website (based on Next.js), typically hosted on a subdomain of [QE Website](https://qepal.com) or a custom domain. It's designed for end-user interaction—especially those unfamiliar with QE—while depending on QE only for back-end infrastructure.

### Server-side Features (Page Backend & GAPI)
- Access to both `udb` (Universal DB) and `xdb` (User DB)
- Supports `Nexus-API Send`, `Nexus-Direct Send`, `Nexus-Channel Send`
- Frontend supports: `Nexus-API Send`, `Nexus-Direct Send`, `Nexus-Channel Send`, `Nexus-Channel Receive`

### Frontend Capabilities
Supports all QE Components, custom tags, and global functions, including login and user-profile functions.

---

## QE Components Available on XWebsite

These are reusable UI utilities designed to reduce redundancy and provide consistent UX:

- **AbbreviateDate** – Localizes date formats
- **Badge** – Displays user privileges
- **bold** – Bolds text using custom fonts
- **FAtoENRatio** – Measures how much of a text is in Persian
- **Circle** – Circular progress indicator
- **Copy** – Copies text to clipboard
- **DropDown** – Collapsible content with title
- **Menu** – Contextual dropdown menu
- **FADigits / EnDigits** – Converts digits between Persian [۰–۹] and Latin [0–9]
- **Flag** – Displays country flags
- **Num2EN / Num2FA** – Converts numbers into English or Persian words
- **Icon2Titles / Icon3Titles** – Image + 2 or 3 lines of descriptive text
- **Img** – Optimized image renderer for icons/signs
- **LinkHasTags** – Converts `#`/`##` prefixed words to clickable links
- **OpeningTitle / OpeningDetails** – Expandable content blocks with titles
- **PhoneEditFloat** – Floating phone input with country code
- **PriceTextBox** – Input/display numeric prices
- **RemainingTime** – Human-readable countdowns
- **ReplacePro** – Inline JSX injection in text
- **Search** – Minimalistic search box
- **StarRating** – Star-based rating UI
- **Text** – Key-value display with optional icon
- **TextArea / TextBox** – Input fields (multi-line or single-line)
- **TextEndAbbreviation / TextMidAbbreviation** – Abbreviates text (end or middle)
- **UserAvatar** – Optimized circular avatar image
- **VItem** – Icon above label text
- **Window / WindowFloat** – Section containers or centered modals
- **ZipAndDownload** – ZIP generator and downloader utility

---

## Global Frontend Functions

- **alerter** – Enhanced alert dialogs
- **api** – Frontend API interface
- **confirmer** – User confirmation dialogs
- **encryptor / decryptor** – Encrypt/decrypt with static password
- **error / success** – Toast notifications
- **serialgenerator** – Generates fixed-length random strings
- **fileexplorer / uploader** – File selection or uploads
- **iconexplorer / linkpicker** – UI explorers for icons or links
- **log** – Sequential UI logs for multi-step actions
- **MD5 / SHA256** – Cryptographic hashing utilities
- **sleep** – Async function delays

### User Auth & Settings (XWebsite Exclusive)

- **loginbyemail / QE / Google / GitHub / LinkedIn / phone** – Auth methods
- **changeenduser.image / name / unit / lang** – Update user profile across QE

---

## Global Server-side Functions (GAPI & Page Backend)

- **api**
- **MD5 / SHA256**
- **serialgenerator**
- **encryptor / decryptor**
- **sleep**

it also has third party library installation capability from `npm`
