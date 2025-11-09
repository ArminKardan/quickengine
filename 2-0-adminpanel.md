
# QE Admin Panel

**QE Admin Panel** is a lightweight, single-page admin panel built on [QE Customized Next.js]() and embedded via iframe into the [QE Website](https://qepal.com). It's used for simplified GUI control of project systems.

## Design Rules
Every QE Developer must obey the [Design Rules](https://qepal.com/docs/1-15-qe-design-rules.md) because of the integrity of system. 


## Pre-Installed Libraries
[Admin Panel Pre-Installed npm libraries](https://qepal.com/docs/1-1-qe-adminpanel-preinstalled.md) on Admin Panel is available and it's recommended to use them over all other libraries.

## Custom tags and QE components
We use [Custom QE Tags](https://qepal.com/docs/1-9-qe-customtags.md) in GUIs as much as possible instead of normal HTML tags.


## Quick Start examples:

> Example 1: [Hello world page](https://qepal.com/docs/examples-helloworld-page.md)

> Example 2: [Hello world component](https://qepal.com/docs/examples-helloworld-component.md)




---



### Admin Panel ready to use components:
We shouldn't recreate components if we need to do some tasks except it's component doesn't exists. It's because of integrity in QE echosystem. Instead we use below components to design Admin Panel Pages:


- [AbbreviateDate](https://qepal.com/docs/1-8-1-qe-qecomps-AbbreviateDate.md) — If we need localized date formatting.
- [Badge](https://qepal.com/docs/1-8-3-qe-qecomps-Bold.md) — If we need: Display user privileges.
- [Bold](https://qepal.com/docs/1-8-3-qe-qecomps-Bold.md) — If we need to bold a text.
- [FAtoENRatio](https://qepal.com/docs/1-8-4-qe-qecomps-FAtoENRatio.md) — If we need to check Persian-to-Latin content ratio.
- [Circle](https://qepal.com/docs/1-8-5-qe-qecomps-Circle.md) — If we need Progress indicator.
- [Copy](https://qepal.com/docs/1-8-6-qe-qecomps-Copy.md) — If we need to Copy some text to the user's clipboard.
- [DropDown](https://qepal.com/docs/1-8-7-qe-qecomps-DropDown.md) — If we need Collapsible UI blocks.
- [Menu](https://qepal.com/docs/1-8-8-qe-qecomps-Menu.md) — If we need Collapsible UI blocks.
- [FADigits](https://qepal.com/docs/1-8-9-qe-qecomps-FaDigits.md) — If we need Convert numerals between Persian and Latin.
- [EnDigits](https://qepal.com/docs/1-8-10-qe-qecomps-EnDigits.md) — If we need Convert numerals between Persian and Latin.
- [Flag](https://qepal.com/docs/1-8-11-qe-qecomps-Flag.md) — If we need Render a country flag.
- [Num2EN](https://qepal.com/docs/1-8-12-qe-qecomps-Num2EN.md) — If we need to Convert numbers to English/Persian words. 
- [Num2FA](https://qepal.com/docs/1-8-13-qe-qecomps-Num2FA.md) — If we need to Convert numbers to English/Persian words.
- [Icon2Titles](https://qepal.com/docs/1-8-14-qe-qecomps-Icon2Titles.md) — If we need to represent 3 titles beside an image. 
- [Icon3Titles](https://qepal.com/docs/1-8-15-qe-qecomps-Icon3Titles.md) — If we need to represent 3 titles beside an image.
- [Img](https://qepal.com/docs/1-8-16-qe-qecomps-Img.md) — If we need Icon/stamp image rendering.
- [LinkHasTags](https://qepal.com/docs/1-8-17-qe-qecomps-LinkHashTags.md) — If we need Convert hashtags to internal links.
- [OpeningTitle](https://qepal.com/docs/1-8-18-qe-qecomps-OpeningTitle-OpeningDetail.md) — If we need Advanced expandable sections. 
- [OpeningDetails](https://qepal.com/docs/1-8-18-qe-qecomps-OpeningTitle-OpeningDetail.md) — If we need Advanced expandable sections.
- [PhoneEditFloat](https://qepal.com/docs/1-8-19-qe-qecomps-PhoneEditFloat.md) — If we need Phone input with country selector.
- [PriceTextBox](https://qepal.com/docs/1-8-20-qe-qecomps-PriceTextBox.md) — If we need  Editable/read-only price input.
- [RemainingTime](https://qepal.com/docs/1-8-21-qe-qecomps-RemainingTime.md) — If we need Human-readable time delta.
- [ReplacePro](https://qepal.com/docs/1-8-22-qe-qecomps-ReplacePro.md) — If we need Inline JSX embedder in text.
- [StarRating](https://qepal.com/docs/1-8-25-qe-qecomps-StarRating.md) — If we need Star-based rating component.
- [TextArea](https://qepal.com/docs/1-8-27-qe-qecomps-TextArea.md) — If we need Text display/input utilities.
- [TextBox](https://qepal.com/docs/1-8-28-qe-qecomps-TextBox.md) — If we need Text display/input utilities.
- [TextEndAbbreviation](https://qepal.com/docs/1-8-29-qe-qecomps-TextEndAbbreviation.md) — If we need Truncate strings smartly.
- [TextMidAbbreviation](https://qepal.com/docs/1-8-30-qe-qecomps-TextMidAbbreviation.md) — If we need Truncate strings smartly.
- [UserAvatar](https://qepal.com/docs/1-8-31-qe-qecomps-UserAvatar.md) — If we need Avatar rendering using Next.js image optimization.
- [VItem](https://qepal.com/docs/1-8-32-qe-qecomps-VItem.md) — If we need Icon + text component.
- [Window](https://qepal.com/docs/1-8-33-qe-qecomps-Window.md) — If we need Primary layout containers.
- [WindowFloat](https://qepal.com/docs/1-8-34-qe-qecomps-WindowFloat.md) — If we need Primary layout containers.
- [ZipAndDownload](https://qepal.com/docs/1-8-35-qe-qecomps-ZipAndDownload.md) — Client-side ZIP file generator.
---

**window (dom) available functions in QE XWebsite page and components:**
- [alerter](https://qepal.com/docs/1-12-qe-front-globals-alerter.md) — If we need to show a message to the user.
- [success](1-12-qe-front-globals-success.md) — If we want to show some simple task successfully done.
- [error](https://qepal.com/docs/1-12-qe-front-globals-error.md) — If we want to show some simple task successfully done.
- [confirmer](https://qepal.com/docs/1-12-qe-front-globals-confirmer.md) — If we need to ask user if they accept an operation to start.
- [api](https://qepal.com/docs/1-12-qe-back-globals-api.md) — Unified GET/POST fetcher.
- [serialgenerator](https://qepal.com/docs/1-12-qe-javascript-globals-serialgenerator.md) — If we need Random string generator.
- [encryptor](https://qepal.com/docs/1-12-qe-javascript-globals-encryptdecrypt.md) — If we need  Symmetric encryption.
- [decryptor](https://qepal.com/docs/1-12-qe-javascript-globals-encryptdecrypt.md) — If we need  Symmetric encryption.
- [fileexplorer](https://qepal.com/docs/1-12-qe-front-globals-fileexplorer.md) — If we need user file upload and manage.
- [iconexplorer](https://qepal.com/docs/1-12-qe-front-globals-iconexplorer.md)  — If we need a SVG Icon using 
- [uploader](https://qepal.com/docs/1-12-qe-javascript-globals-uploader.md) — If we need to upload a file to CDN.
- [linkpicker](https://qepal.com/docs/1-12-qe-front-globals-linkpicker.md) — If we need to upload a file to CDN or select from previous links or set a link directly by textbox.
- [log](https://qepal.com/docs/1-12-qe-front-globals-log.md) — User-facing sequential logs.
- [MD5](https://qepal.com/docs/1-12-qe-javascript-globals-md5.md) — Hash functions.
- [SHA256](https://qepal.com/docs/1-12-qe-javascript-globals-sha256.md) — Hash functions.
- [sleep](https://qepal.com/docs/1-12-qe-javascript-globals-sleep.md) — Async delay.
- [udb](https://qepal.com/docs/1-15-qe-nodejs-udb.md) If wee need to connect to the MongoDB database of XWebsite (Available to [topuser](https://qepal.com/docs/1-15-qe-xwebsite-xdb.md).


###  GAPI (Both Browser & Server Side RestAPI communication)
- [GAPI](https://qepal.com/docs/1-15-qe-back-gapi.md) — If we need to send/receive data with backend (for example mongodb) by RestAPI after page has been created we use GAPI system. Note that it cannot communicate with workers.

###  Nexus Methods (Both Browser & Server Side)
- [Nexus Find](https://qepal.com/docs/1-11-qe-nexus.md) — If we need to find available workers of some service.
- [Nexus API Send](https://qepal.com/docs/1-11-qe-nexus.md) — If we need to send a message to a worker using nexus and get it's response back.
- [Nexus Channel Send](https://qepal.com/docs/1-11-qe-nexus.md) — If we need to send a message to a worker using nexus and get it's response back.

- [Nexus Channel Receive](https://qepal.com/docs/1-11-qe-nexus.md) — If we need to send a message to a worker using nexus and get it's response back.

- [Nexus Direct Send](https://qepal.com/docs/1-11-qe-nexus.md) — If we need to send a message to a QE block using their JID and resource.

###  Nexus Methods (Server Side)
- [Nexus Direct Receive](https://qepal.com/docs/1-11-qe-nexus.md) — If we need to send a message to a QE block using their JID and resource.


## Summary

QE Admin Panel is a powerful and minimal environment that integrates seamlessly with QE infrastructure. It leverages reusable QE components, global functions, and Nexus/UDb features to create efficient, maintainable admin tools.
