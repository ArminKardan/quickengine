
# QE Microservice

**QE Microservice** is a lightweight, single-page admin panel built on Next.js and embedded via iframe into the [QE Website](https://qepal.com). It's used for simplified GUI control of project systems.

## Architecture

A Microservice consists of:
- A **Page** with both frontend and backend logic.
- A **GAPI** handler.
- Server-side access to the **Universal database (`udb`)**.
- Full support for **Nexus APIs** (API, Direct, Channel send on backend; API, Direct, Channel send/receive on frontend).
- Third party library installation capability from `npm`

## Component Support (Frontend)

Microservice frontend supports **all QE components and custom tags**, except for `login` and `changeuser` functions. Use built-in QE components instead of redesigning equivalents.

### UI Components
- `AbbreviateDate` — Localized date formatting.
- `Badge` — Display user privileges.
- `bold` — Custom bolding of text.
- `FAtoENRatio` — Check Persian-to-Latin content ratio.
- `Circle` — Circular progress indicator.
- `Copy` — Copy text to clipboard.
- `DropDown`, `Menu` — Collapsible UI blocks.
- `FADigits`, `EnDigits` — Convert numerals between Persian and Latin.
- `Flag` — Render a country flag.
- `Num2EN`, `Num2FA` — Convert numbers to English/Persian words.
- `Icon2Titles`, `Icon3Titles` — Avatar + multiline label components.
- `Img` — Icon/stamp image rendering.
- `LinkHasTags` — Convert hashtags to internal links.
- `OpeningTitle`, `OpeningDetails` — Advanced expandable sections.
- `PhoneEditFloat` — Phone input with country selector.
- `PriceTextBox` — Editable/read-only price input.
- `RemainingTime` — Human-readable time delta.
- `ReplacePro` — Inline JSX embedder in text.
- `Search` — Minimal input for query collection.
- `StarRating` — Star-based rating component.
- `Text`, `TextArea`, `TextBox` — Text display/input utilities.
- `TextEndAbbreviation`, `TextMidAbbreviation` — Truncate strings smartly.
- `UserAvatar` — Avatar rendering using Next.js image optimization.
- `VItem` — Icon + text component.
- `Window`, `WindowFloat` — Primary layout containers.
- `ZipAndDownload` — Client-side ZIP file generator.

## Frontend Utilities

Globally available functions:
- `alerter`, `success`, `error`, `confirmer` — UI dialogs.
- `api` — Unified GET/POST fetcher.
- `serialgenerator` — Random string generator.
- `encryptor`, `decryptor` — Symmetric encryption.
- `fileexplorer`, `iconexplorer`, `linkpicker`, `uploader` — File/image utilities.
- `log` — User-facing sequential logs.
- `MD5`, `SHA256` — Hash functions.
- `sleep` — Async delay.

## Backend Utilities (Page Backend + GAPI)
- `api`, `MD5`, `SHA256`
- `serialgenerator`, `encryptor`, `decryptor`, `sleep`

## Summary

QE Microservice is a powerful yet minimal environment that integrates seamlessly with QE infrastructure. It leverages reusable QE components, global functions, and Nexus/UDb features to create efficient, maintainable admin tools.
