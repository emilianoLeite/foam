# [Viral Options](https://frontendmasters.com/courses/production-typescript/viral-options/)

_from FrontendMasters'_ Production-Grade TypeScript _course, by Mike North_

[course repo](https://github.com/mike-north/professional-ts/)

- The viral options are
  - `allowSyntheticDefaultImports`
  - `esModuleInterop`
  - `skipLibCheck`
  
He says that this options are "viral" in the sense of a impure function. If you enable these flags, the consumers of your library most likely will have to enable them as well.

As previously mentioned, it is more important to avoid these options when developing a library, and not so critical when developing an app.

Some workarounds when these flags are disabled are:

### Example 1
```ts
// file legacy.js - CommonJS module
function product(a, b) {
  return a * b
}

module.exports = { product }

// file consumer.ts
import { product } from "./legacy"
// this is a case where CommonJS and ESModules are in harmony, things "just work"
```

### Example 2
```ts
// file consumer.ts

// with esModuleInterop enabled we can import a namespace as a default export
// This means we could do
import fs from "fs"
// instead of
import * as fs from "fs"
```

### Example 3
```ts
// file legacy.js - CommonJS module
function product(a, b) {
  return a * b
}

module.exports = product

// file consumer.ts
import product = require("./legacy")
```