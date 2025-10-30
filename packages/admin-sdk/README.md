  # meteor-admin-sdk
[![Tests](https://github.com/onlishop/meteor-admin-sdk/actions/workflows/tests.yml/badge.svg)](https://github.com/onlishop/meteor-admin-sdk/actions/workflows/tests.yml)
[![NPM Package](https://img.shields.io/npm/v/@onlishop/meteor-admin-sdk)](https://www.npmjs.com/package/@onlishop/meteor-admin-sdk)

The `meteor-admin-sdk` is a JavaScript library for all [Onlishop 6](https://github.com/onlishop/platform) App and Plugin developer which want an easy way to extend and customize the administration.

[See Documentation](https://developer.onlishop.com/resources/admin-extension-sdk/)

## Installation
#### Using NPM:
Install it to your `package.json`
```
npm i --save @onlishop/meteor-admin-sdk
```

and import it in your app:
```js
// import everything
import * as sw from '@onlishop/meteor-admin-sdk';

// or import only needed functionality
import { notification }  from '@onlishop/meteor-admin-sdk';
```

#### Using CDN:
Import the source from the CDN

```js
// use the latest version available
<script src="https://unpkg.com/@onlishop/meteor-admin-sdk/cdn"></script>

// use a fix version (example here: 1.2.3)
<script src="https://unpkg.com/@onlishop/meteor-admin-sdk@1.2.3/cdn"></script>
```

and then you can access it with the global variable `sw`.

```js
sw.notification.dispatch({
  title: 'My first notification',
  message: 'This was really easy to do'
})
```

## Features
- 🏗  **Works with Onlishop 6 Apps and Plugins:** you can use the SDK for your plugins or apps. API usage is identical.
- 🎢  **Shallow learning curve:** you don't need to have extensive knowledge about the internals of the Onlishop 6 Administration. Our SDK hides the complicated stuff behind a beautiful API.
- 🧰  **Many extension capabilities:** from throwing notifications, accessing context information or extending the current UI. The feature set of the SDK will gradually be extended, providing more possibilities and flexibility for your ideas and solutions.
- 🪨  **A stable API with great backwards compatibility:** don't fear Onlishop updates anymore. Breaking changes in this SDK are an exception. If you use the SDK, your apps and plugins will stay stable for a longer time, without any need for code maintenance.
- 🧭  **Type safety:** the whole SDK is written in TypeScript which provides great autocompletion support and more safety for your apps and plugins.
- 💙  **Developer experience:** have a great development experience right from the start. And it will become better and better in the future.
- 🪶  **Lightweight:** the whole library is completely tree-shakable and dependency-free. Every functionality can be imported granularly to keep your bundle as small and fast as possible.

## Examples

Throw a notification:
```js
sw.notification.dispatch({
  title: 'My first notification',
  message: 'This was really easy to do'
})
```

Get the system currency:
```js
const currency = await sw.context.getCurrency();
```

Subscribe for UI locale changes:
```js
let currentLocale = 'en-GB';

sw.context.subscribeLocale(({ locale }) => {
  currentLocale = locale;
})
```

See more examples in the [Documentation](https://developer.onlishop.com/resources/admin-extension-sdk/).
