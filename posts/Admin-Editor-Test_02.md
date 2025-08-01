---
title: 'Admin Editor '
description: A new post
date: '2025-07-28'
author: Your Name
tags:
  - Editor
  - Gemini
  - Preplixity
slug: new-post
image: >-
  https://images.unsplash.com/photo-1571244051166-5548e340b792?q=80&w=1074&auto=format&fit=crop&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D
category: Admin
---

# From Admin Editor

Start writing your Markdown content here.

<img src="https://r2cdn.perplexity.ai/pplx-full-logo-primary-dark%402x.png" class="logo" width="120"/>

## Why You're Seeing This Type Error

The error:

```
Type error: Module '"@/lib/github-admin"' declares 'GITHUB_CONTENT_PATH' locally, but it is not exported.
```

means that `GITHUB_CONTENT_PATH` exists in your `@/lib/github-admin` file but is not exported with the `export` keyword. In TypeScript (and JavaScript ES modules), you can only import variables, functions, or types that have been explicitly exported from the other file[^1][^2][^3].

## How to Fix the Error

### 1. Export the Constant in `github-admin.ts`

Open your `lib/github-admin.ts` file and find the line:

```ts
const GITHUB_CONTENT_PATH = process.env.GITHUB_CONTENT_PATH as string;
```

Change it to:

```ts
export const GITHUB_CONTENT_PATH = process.env.GITHUB_CONTENT_PATH as string;
```

Do this for any other similar constants if you intend to share them across modules.

### 2. Verify and Save

- Save the updated file.
- Now re-run your build. The error should disappear since the constant is now available for import.


### 3. General Pattern: Exporting Constants

This is the recommended pattern when you want to reuse values from one module in another:

```ts
// file: my-constants.ts
export const SOMETHING = "value";

// file: other-file.ts
import { SOMETHING } from './my-constants';
```

If you forget the `export` keyword, anything declared in the file is only available locally, not for imports in other files[^1][^2].

## Best Practices

- Only import constants that are exported from the source module.
- For sensitive settings like environment variables, consider creating a dedicated config file and only exporting what you truly need to expose elsewhere[^4][^5].
- In most Next.js applications, you access environment variables via `process.env` directly inside the function or API handler, especially for server-side files[^6][^7]. If `GITHUB_CONTENT_PATH` is meant only for use within `lib/github-admin.ts`, no export is needed and you can access `process.env.GITHUB_CONTENT_PATH` in each file where needed.


## Summary Table

| File Change | What To Do |
| :-- | :-- |
| `lib/github-admin.ts` | Add `export` to the constant declaration |
| Anywhere you import | Use standard import syntax |

**Example:**

```ts
// lib/github-admin.ts
export const GITHUB_CONTENT_PATH = process.env.GITHUB_CONTENT_PATH as string;

// admin/delete/route.ts
import { GITHUB_CONTENT_PATH } from '@/lib/github-admin';
```

Once you export the constant, this type error will be resolved. If you have further issues, double-check the spelling and capitalization of both the variable and its import name[^1].

<div style="text-align: center">⁂</div>

[^1]: https://bobbyhadz.com/blog/typescript-module-has-no-exported-member

[^2]: https://www.codepedia.org/snippets/5fcf18bf781081728180314b/how-to-export-a-constant-in-typescript

[^3]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/export

[^4]: https://dev.to/austinshelby/you-are-reading-environment-variables-the-wrong-way-in-nextjs-45da

[^5]: https://dev.to/dipakkr/best-practises-for-loading-environment-variable-in-nextjs-application-3hni

[^6]: https://nextjs.org/docs/pages/guides/environment-variables

[^7]: https://refine.dev/blog/next-js-environment-variables/

[^8]: https://stackoverflow.com/questions/60740708/module-declares-component-locally-but-it-is-not-exported

[^9]: https://www.typescriptlang.org/tsconfig/isolatedModules.html

[^10]: https://www.reddit.com/r/typescript/comments/o8m2ee/error_module_typescriptdeclarations_has_no/

[^11]: https://github.com/microsoft/TypeScript/issues/29624

[^12]: https://stackoverflow.com/questions/69511161/export-all-constants-from-files-into-index-ts-and-then-export-those-constants-as

[^13]: https://www.typescriptlang.org/docs/handbook/modules/reference.html

[^14]: https://typescript.tv/errors

[^15]: https://stackoverflow.com/questions/39385933/cant-export-constant-in-typescript

[^16]: https://github.com/colinhacks/zod/issues/3739

[^17]: https://dev.to/amirfakour/tips-to-use-constants-file-in-typescript-27je

[^18]: https://stackoverflow.com/questions/43900035/ts4023-exported-variable-x-has-or-is-using-name-y-from-external-module-but/69870219

[^19]: https://www.dhiwise.com/post/how-to-manage-nextjs-environment-variables-for-better-security

[^20]: https://www.totaltypescript.com/books/total-typescript-essentials/modules-scripts-and-declaration-files

