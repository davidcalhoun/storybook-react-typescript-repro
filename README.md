# storybook-react-typescript-repo

This is a simple reproduction to illustrate an apparent error using Storybook with TypeScript and React.

Storybook issue: https://github.com/storybookjs/storybook/issues/17589

## Installation

1. `git clone git@github.com:davidcalhoun/storybook-react-typescript-repro.git && cd storybook-react-typescript-repro`
1. `yarn install`
1. `yarn storybook`

## Steps to recreate from scratch

1. Create a Storybook repo via [these steps](https://storybook.js.org/docs/react/contribute/how-to-reproduce).  In short: `npx sb@next repro`, select `react` for a framework, select `react_typescript` for a base template, then choose any name for the output directory.
1. Rename the file `.storybook/main.js` to `.storybook/main.ts` (converts it to TypeScript)
1. Add any ESM import/export to the top of `.storybook/main.ts`.  For this repo I've used a type import from the [Storybook react-ts example](https://github.com/storybookjs/storybook/blob/v6.5.0-alpha.42/examples/react-ts/.storybook/main.ts#L1).
1. `yarn storybook` and note the parse error.

## Error output

### Output from the repro above

```
dcalhoun@Davids-MacBook-Pro-2 storybook-react-typescript-repro % yarn storybook
info @storybook/react v6.5.0-alpha.42
info
ERR! SyntaxError: /Users/dcalhoun/dev/storybook-react-typescript-repro/.storybook/main.ts: Unexpected token, expected "from" (1:12)
ERR!
ERR! > 1 | import type { StorybookConfig } from '@storybook/react/types';
ERR!     |             ^
ERR!   2 |
ERR!   3 | module.exports = {
ERR!   4 |   "stories": [
ERR!     at Parser._raise (/Users/dcalhoun/dev/storybook-react-typescript-repro/node_modules/@babel/parser/lib/index.js:476:17)
ERR!     at Parser.raiseWithData (/Users/dcalhoun/dev/storybook-react-typescript-repro/node_modules/@babel/parser/lib/index.js:469:17)
ERR!     at Parser.raise (/Users/dcalhoun/dev/storybook-react-typescript-repro/node_modules/@babel/parser/lib/index.js:430:17)
ERR!     at Parser.unexpected (/Users/dcalhoun/dev/storybook-react-typescript-repro/node_modules/@babel/parser/lib/index.js:3789:16)
ERR!     at Parser.expectContextual (/Users/dcalhoun/dev/storybook-react-typescript-repro/node_modules/@babel/parser/lib/index.js:3744:18)
ERR!     at Parser.parseImport (/Users/dcalhoun/dev/storybook-react-typescript-repro/node_modules/@babel/parser/lib/index.js:15704:12)
ERR!     at Parser.parseStatementContent (/Users/dcalhoun/dev/storybook-react-typescript-repro/node_modules/@babel/parser/lib/index.js:14223:27)
ERR!     at Parser.parseStatement (/Users/dcalhoun/dev/storybook-react-typescript-repro/node_modules/@babel/parser/lib/index.js:14113:17)
ERR!     at Parser.parseBlockOrModuleBlockBody (/Users/dcalhoun/dev/storybook-react-typescript-repro/node_modules/@babel/parser/lib/index.js:14739:25)
ERR!     at Parser.parseBlockBody (/Users/dcalhoun/dev/storybook-react-typescript-repro/node_modules/@babel/parser/lib/index.js:14730:10)
ERR!     at Parser.parseProgram (/Users/dcalhoun/dev/storybook-react-typescript-repro/node_modules/@babel/parser/lib/index.js:14032:10)
ERR!     at Parser.parseTopLevel (/Users/dcalhoun/dev/storybook-react-typescript-repro/node_modules/@babel/parser/lib/index.js:14019:25)
ERR!     at Parser.parse (/Users/dcalhoun/dev/storybook-react-typescript-repro/node_modules/@babel/parser/lib/index.js:15940:10)
ERR!     at parse (/Users/dcalhoun/dev/storybook-react-typescript-repro/node_modules/@babel/parser/lib/index.js:15992:38)
ERR!     at parser (/Users/dcalhoun/dev/storybook-react-typescript-repro/node_modules/@babel/core/lib/parser/index.js:52:34)
ERR!     at parser.next (<anonymous>)
ERR!  SyntaxError: /Users/dcalhoun/dev/storybook-react-typescript-repro/.storybook/main.ts: Unexpected token, expected "from" (1:12)
ERR!
ERR! > 1 | import type { StorybookConfig } from '@storybook/react/types';
ERR!     |             ^
ERR!   2 |
ERR!   3 | module.exports = {
ERR!   4 |   "stories": [
ERR!     at Parser._raise (/Users/dcalhoun/dev/storybook-react-typescript-repro/node_modules/@babel/parser/lib/index.js:476:17)
ERR!     at Parser.raiseWithData (/Users/dcalhoun/dev/storybook-react-typescript-repro/node_modules/@babel/parser/lib/index.js:469:17)
ERR!     at Parser.raise (/Users/dcalhoun/dev/storybook-react-typescript-repro/node_modules/@babel/parser/lib/index.js:430:17)
ERR!     at Parser.unexpected (/Users/dcalhoun/dev/storybook-react-typescript-repro/node_modules/@babel/parser/lib/index.js:3789:16)
ERR!     at Parser.expectContextual (/Users/dcalhoun/dev/storybook-react-typescript-repro/node_modules/@babel/parser/lib/index.js:3744:18)
ERR!     at Parser.parseImport (/Users/dcalhoun/dev/storybook-react-typescript-repro/node_modules/@babel/parser/lib/index.js:15704:12)
ERR!     at Parser.parseStatementContent (/Users/dcalhoun/dev/storybook-react-typescript-repro/node_modules/@babel/parser/lib/index.js:14223:27)
ERR!     at Parser.parseStatement (/Users/dcalhoun/dev/storybook-react-typescript-repro/node_modules/@babel/parser/lib/index.js:14113:17)
ERR!     at Parser.parseBlockOrModuleBlockBody (/Users/dcalhoun/dev/storybook-react-typescript-repro/node_modules/@babel/parser/lib/index.js:14739:25)
ERR!     at Parser.parseBlockBody (/Users/dcalhoun/dev/storybook-react-typescript-repro/node_modules/@babel/parser/lib/index.js:14730:10)
ERR!     at Parser.parseProgram (/Users/dcalhoun/dev/storybook-react-typescript-repro/node_modules/@babel/parser/lib/index.js:14032:10)
ERR!     at Parser.parseTopLevel (/Users/dcalhoun/dev/storybook-react-typescript-repro/node_modules/@babel/parser/lib/index.js:14019:25)
ERR!     at Parser.parse (/Users/dcalhoun/dev/storybook-react-typescript-repro/node_modules/@babel/parser/lib/index.js:15940:10)
ERR!     at parse (/Users/dcalhoun/dev/storybook-react-typescript-repro/node_modules/@babel/parser/lib/index.js:15992:38)
ERR!     at parser (/Users/dcalhoun/dev/storybook-react-typescript-repro/node_modules/@babel/core/lib/parser/index.js:52:34)
ERR!     at parser.next (<anonymous>) {
ERR!   loc: Position { line: 1, column: 12, index: 12 },
ERR!   pos: 12,
ERR!   code: 'BABEL_PARSE_ERROR',
ERR!   reasonCode: 'UnexpectedToken'
ERR! }

WARN Broken build, fix the error above.
WARN You may need to refresh the browser.
```

### Example from a different project using an ESM export on the first line of its `main.ts`

```
% yarn workspace [REDACTED] start-storybook -p 6006
info @storybook/react v6.4.19
info
ERR! /Users/dcalhoun/dev/[REDACTED]/packages/app/.storybook/main.ts:1
ERR! export * from '[REDACTED]/config/storybook/main';
ERR! ^^^^^^
ERR!
ERR! SyntaxError: Unexpected token 'export'
ERR!     at Object.compileFunction (node:vm:352:18)
ERR!     at wrapSafe (node:internal/modules/cjs/loader:1031:15)
ERR!     at Module._compile (node:internal/modules/cjs/loader:1065:27)
ERR!     at Module._compile (/Users/dcalhoun/dev/[REDACTED]/.yarn/cache/pirates-npm-4.0.1-377058e8fc-091e232aac.zip/node_modules/pirates/lib/index.js:99:24)
ERR!     at Module._extensions..js (node:internal/modules/cjs/loader:1153:10)
ERR!     at Object.newLoader [as .ts] (/Users/dcalhoun/dev/[REDACTED]/.yarn/cache/pirates-npm-4.0.1-377058e8fc-091e232aac.zip/node_modules/pirates/lib/index.js:104:7)
ERR!     at Module.load (node:internal/modules/cjs/loader:981:32)
ERR!     at Function.external_module_.Module._load (/Users/dcalhoun/dev/[REDACTED]/.pnp.cjs:47551:14)
ERR!     at Module.require (node:internal/modules/cjs/loader:1005:19)
ERR!     at require (node:internal/modules/cjs/helpers:102:18)
ERR!     at interopRequireDefault (/Users/dcalhoun/dev/[REDACTED]/.yarn/__virtual__/@storybook-core-common-virtual-efc08e55c3/0/cache/@storybook-core-common-npm-6.4.19-54b55d19ba-3f10064014.zip/node_modules/@storybook/core-common/dist/cjs/utils/interpret-require.js:64:16)
ERR!     at serverRequire (/Users/dcalhoun/dev/[REDACTED]/.yarn/__virtual__/@storybook-core-common-virtual-efc08e55c3/0/cache/@storybook-core-common-npm-6.4.19-54b55d19ba-3f10064014.zip/node_modules/@storybook/core-common/dist/cjs/utils/interpret-require.js:101:10)
ERR!     at getPreviewBuilder (/Users/dcalhoun/dev/[REDACTED]/.yarn/__virtual__/@storybook-core-server-virtual-c36c68fb38/0/cache/@storybook-core-server-npm-6.4.19-9c09ed894e-7c601f1bbf.zip/node_modules/@storybook/core-server/dist/cjs/utils/get-preview-builder.js:25:55)
ERR!     at buildDevStandalone (/Users/dcalhoun/dev/[REDACTED]/.yarn/__virtual__/@storybook-core-server-virtual-c36c68fb38/0/cache/@storybook-core-server-npm-6.4.19-9c09ed894e-7c601f1bbf.zip/node_modules/@storybook/core-server/dist/cjs/build-dev.js:102:71)
ERR!     at buildDev (/Users/dcalhoun/dev/[REDACTED]/.yarn/__virtual__/@storybook-core-server-virtual-c36c68fb38/0/cache/@storybook-core-server-npm-6.4.19-9c09ed894e-7c601f1bbf.zip/node_modules/@storybook/core-server/dist/cjs/build-dev.js:161:5)
ERR!  /Users/dcalhoun/dev/[REDACTED]/packages/app/.storybook/main.ts:1
```