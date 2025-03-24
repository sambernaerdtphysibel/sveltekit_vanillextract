# sveltekit_vanillextract

Sample setup SvelteKit and Vanilla Extract that showcases the issue with

- Sveltekit + vanilla extract + monorepo

### Summary of setup

- Initialize repo with `npx create-turbo@latest -e with-svelte`
- Add vanilla extract to package `ui/`
- Use style in app `web/`

### Issue

- `cd apps/web`
- `pnpm run dev`

Result:

```
Styles were unable to be assigned to a file. This is generally caused by one of the following:

- You may have created styles outside of a '.css.ts' context
- You may have incorrect configuration. See https://vanilla-extract.style/documentation/getting-started

Error: Styles were unable to be assigned to a file. This is generally caused by one of the following:

- You may have created styles outside of a '.css.ts' context
- You may have incorrect configuration. See https://vanilla-extract.style/documentation/getting-started
    at Object.getFileScope (C:\Dev\Misc\sveltekit_vanillextract\repo\node_modules\.pnpm\@vanilla-extract+css@1.17.1\node_modules\@vanilla-extract\css\fileScope\dist\vanilla-extract-css-fileScope.cjs.dev.js:35:11)
    at generateIdentifier (C:\Dev\Misc\sveltekit_vanillextract\repo\node_modules\.pnpm\@vanilla-extract+css@1.17.1\node_modules\@vanilla-extract\css\dist\vanilla-extract-css.cjs.dev.js:155:49)
    at style (C:\Dev\Misc\sveltekit_vanillextract\repo\node_modules\.pnpm\@vanilla-extract+css@1.17.1\node_modules\@vanilla-extract\css\dist\vanilla-extract-css.cjs.dev.js:415:19)
    at C:\Dev\Misc\sveltekit_vanillextract\repo\packages\ui\styles\someStyle.css.ts:3:26
    at async ESModulesEvaluator.runInlinedModule (file:///C:/Dev/Misc/sveltekit_vanillextract/repo/node_modules/.pnpm/vite@6.2.0/node_modules/vite/dist/node/module-runner.js:1049:5)
    at async SSRCompatModuleRunner.directRequest (file:///C:/Dev/Misc/sveltekit_vanillextract/repo/node_modules/.pnpm/vite@6.2.0/node_modules/vite/dist/node/module-runner.js:1271:61)
    at async SSRCompatModuleRunner.directRequest (file:///C:/Dev/Misc/sveltekit_vanillextract/repo/node_modules/.pnpm/vite@6.2.0/node_modules/vite/dist/node/chunks/dep-ByPKlqZ5.js:30913:23)
    at async SSRCompatModuleRunner.cachedRequest (file:///C:/Dev/Misc/sveltekit_vanillextract/repo/node_modules/.pnpm/vite@6.2.0/node_modules/vite/dist/node/module-runner.js:1167:76)
    at async eval (C:\Dev\Misc\sveltekit_vanillextract\repo\packages\ui\index.ts:2:1)
    at async ESModulesEvaluator.runInlinedModule (file:///C:/Dev/Misc/sveltekit_vanillextract/repo/node_modules/.pnpm/vite@6.2.0/node_modules/vite/dist/node/module-runner.js:1
```
