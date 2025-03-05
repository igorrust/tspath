# tsx issue with tsconfig paths

## Context
Issue related to https://github.com/privatenumber/tsx dependency

## Reproduction
- 🆗 Run `npm run test` which correctly prints "Markdown" to the console 
- ❌ Run `npm run test-alias` which prints the following to the console:

    ```
    PS C:\src\playground\tspath> npm run test-alias

    > tspath@1.0.0 test-alias
    > tsx ./scripts/test-script/test-script-alias.ts

    node:internal/modules/cjs/loader:1244
    const err = new Error(message);
                ^

    Error: Cannot find module '#shared/constants'
    Require stack:
    - C:\src\playground\tspath\scripts\test-script\test-script-alias.ts
        at node:internal/modules/cjs/loader:1244:15
        at nextResolveSimple (C:\src\playground\tspath\node_modules\tsx\dist\register-DCnOAxY2.cjs:3:942)
        at C:\src\playground\tspath\node_modules\tsx\dist\register-DCnOAxY2.cjs:2:2550
        at C:\src\playground\tspath\node_modules\tsx\dist\register-DCnOAxY2.cjs:2:1624
        at resolveTsPaths (C:\src\playground\tspath\node_modules\tsx\dist\register-DCnOAxY2.cjs:3:760)
        at C:\src\playground\tspath\node_modules\tsx\dist\register-DCnOAxY2.cjs:3:1038
        at m._resolveFilename (file:///C:/src/playground/tspath/node_modules/tsx/dist/register-RyGUjI6j.mjs:1:789)
        at Function._load (node:internal/modules/cjs/loader:1070:27)
        at TracingChannel.traceSync (node:diagnostics_channel:322:14)
        at wrapModuleLoad (node:internal/modules/cjs/loader:217:24) {
    code: 'MODULE_NOT_FOUND',
    requireStack: [
        'C:\\src\\playground\\tspath\\scripts\\test-script\\test-script-alias.ts'
    ]
    }

    Node.js v22.13.0
    ```
