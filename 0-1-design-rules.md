# QE Design rules

There is some rules of designing by QE that make project designs integrated and they are highly recommended to follow.

## Project Types
In this system, projects are categorized into two main types:

### Middleware Projects
These are reusable components or services that provide supporting functionality across multiple parts of the system. They are not user-facing but serve as foundational building blocks.

### Product Projects
These represent the core applications or services delivered to end users. They may rely on some middleware projects to function but define the primary business logic and user-facing features.


## No React Hooks in GUIs
We never use react hooks until it's inevitable. developers must not use useEffect, useState, useRef instead we will use [Framer Motion](https://motion.dev/), props, refresh

## Admin Panel or Xwebsite?
We will use Admin Panel as an admin pannel and.
Admin Panel is recommended to be single page.
Xwebsite as multiple page.
If Product can be single page use Admin Panel.
Otherwise use Admin Panel as admin panel and XWebsite as product page.

## Send data from frontend to backend 
For sending data from page's front end to the backend of the same block we use GAPI.

## Sending data from frontend to backend of another block:
here we use GAPI on destination block and use `api` global function to send data.



## Custom tags and QE components
We use custom tags in GUIs as much as possible instead of normal HTML tags.

## Installing Third party librarues

We install third party libraries only if there is no clean way.

## Nodejs worker is primary choice to design

We use nodejs worker over other types of worker if its possible and we use other types if designing will be much esasier using them or we need a third party library that is only available on other type of worker.

## Python workers for AI
We use only python workers when we're going to do some machine learning, data science related or AI works to do.

## Nexus vs Rest API:
We only use Rest API's on workers when we need a standard communication way from outside of QE or when there is absolutely no need for Identity validating.



