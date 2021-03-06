---
title: 'nuxt.renderAndGetWindow(url, options)'
description: Get the `window` from a given URL of a Nuxt.js Application.
menu: renderAndGetWindow
category: internals-glossary
position: 12
---

- Type: `Function`
- Argument: `String`
  1. `String`: URL to render
  2. _Optional_, `Object`: options
  - virtualConsole: `Boolean` (default: `true`)
- Returns: `Promise`
  - Returns: `window`

> Get the window from a given url of a Nuxt.js application.

<base-alert>

This method is made for test purposes.

</base-alert>

To use this function, you have to install `jsdom`:

```bash
npm install --save-dev jsdom
```

Example:

```js
const { loadNuxt } = require('nuxt')

async function init() {
  // Assuming you've already built your project
  const nuxt = await loadNuxt({ for: 'start' })
  await nuxt.listen(3000)
  const window = await nuxt.renderAndGetWindow('http://localhost:3000')
  // Display the head `<title>`
  console.log(window.document.title)
  nuxt.close()
}

init()
```
