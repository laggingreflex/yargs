# Changelog

All notable changes to this project will be documented in this file. See [standard-version](https://github.com/conventional-changelog/standard-version) for commit guidelines.

## [15.2.0](https://www.github.com/laggingreflex/yargs/compare/v15.1.0...v15.2.0) (2021-01-11)


### ⚠ BREAKING CHANGES

* #1823 contains the following breaking API changes:
    * now returns a promise if handler is async.
    * onFinishCommand removed, in favor of being able to await promise.
    * getCompletion now invokes callback with err and `completions, returns promise of completions.
* tweaks to ESM/Deno API surface: now exports yargs function by default; getProcessArgvWithoutBin becomes hidBin; types now exported for Deno.
* find-up replaced with escalade; export map added (limits importable files in Node >= 12); yarser-parser@19.x.x (new decamelize/camelcase implementation).
* **usage:** single character aliases are now shown first in help output
* **ts:** yargs now ships with its own types
* drop support for EOL Node 8 (#1686)
* **deps:** yargs-parser@17.0.0 no longer implicitly creates arrays out of boolean arguments when duplicates are provided

### Features

* add usage for single-digit boolean aliases ([#1580](https://www.github.com/laggingreflex/yargs/issues/1580)) ([6014e39](https://www.github.com/laggingreflex/yargs/commit/6014e39bca3a1e8445aa0fb2a435f6181e344c45))
* adds deprecation option for commands ([027a636](https://www.github.com/laggingreflex/yargs/commit/027a6365b737e13116811a8ef43670196e1fa00a))
* adds strictOptions() ([#1738](https://www.github.com/laggingreflex/yargs/issues/1738)) ([b215fba](https://www.github.com/laggingreflex/yargs/commit/b215fba0ed6e124e5aad6cf22c8d5875661c63a3))
* adds support for ESM and Deno ([#1708](https://www.github.com/laggingreflex/yargs/issues/1708)) ([ac6d5d1](https://www.github.com/laggingreflex/yargs/commit/ac6d5d105a75711fe703f6a39dad5181b383d6c6))
* command() now accepts an array of modules ([f415388](https://www.github.com/laggingreflex/yargs/commit/f415388cc454d02786c65c50dd6c7a0cf9d8b842))
* **completion:** takes negated flags into account when boolean-negation is set ([#1509](https://www.github.com/laggingreflex/yargs/issues/1509)) ([7293ad5](https://www.github.com/laggingreflex/yargs/commit/7293ad50d20ea0fb7dd1ac9b925e90e1bd95dea8))
* deprecateOption ([#1559](https://www.github.com/laggingreflex/yargs/issues/1559)) ([8aae333](https://www.github.com/laggingreflex/yargs/commit/8aae3332251d09fa136db17ef4a40d83fa052bc4))
* **deps:** pull in yargs-parser@17.0.0 ([#1553](https://www.github.com/laggingreflex/yargs/issues/1553)) ([b9409da](https://www.github.com/laggingreflex/yargs/commit/b9409da199ebca515a848489c206b807fab2e65d))
* **deps:** yargs-parser with 'greedy-array' configuration ([#1569](https://www.github.com/laggingreflex/yargs/issues/1569)) ([a03a320](https://www.github.com/laggingreflex/yargs/commit/a03a320dbf5c0ce33d829a857fc04a651c0bb53e))
* display appropriate $0 for electron apps ([#1536](https://www.github.com/laggingreflex/yargs/issues/1536)) ([d0e4379](https://www.github.com/laggingreflex/yargs/commit/d0e437912917d6a66bb5128992fa2f566a5f830b))
* drop support for EOL Node 8 ([#1686](https://www.github.com/laggingreflex/yargs/issues/1686)) ([863937f](https://www.github.com/laggingreflex/yargs/commit/863937f23c3102f804cdea78ee3097e28c7c289f))
* expose hideBin helper for CJS ([#1768](https://www.github.com/laggingreflex/yargs/issues/1768)) ([63e1173](https://www.github.com/laggingreflex/yargs/commit/63e1173bb47dc651c151973a16ef659082a9ae66))
* **helpers:** rebase, Parser, applyExtends now blessed helpers ([#1733](https://www.github.com/laggingreflex/yargs/issues/1733)) ([c7debe8](https://www.github.com/laggingreflex/yargs/commit/c7debe8eb1e5bc6ea20b5ed68026c56e5ebec9e1))
* i18n for ESM and Deno ([#1735](https://www.github.com/laggingreflex/yargs/issues/1735)) ([c71783a](https://www.github.com/laggingreflex/yargs/commit/c71783a5a898a0c0e92ac501c939a3ec411ac0c1))
* improve support for async/await ([#1823](https://www.github.com/laggingreflex/yargs/issues/1823)) ([169b815](https://www.github.com/laggingreflex/yargs/commit/169b815df7ae190965f04030f28adc3ab92bb4b5))
* introduces strictCommands() subset of strict mode ([#1540](https://www.github.com/laggingreflex/yargs/issues/1540)) ([1d4cca3](https://www.github.com/laggingreflex/yargs/commit/1d4cca395a98b395e6318f0505fc73bef8b01350))
* support array of examples ([#1682](https://www.github.com/laggingreflex/yargs/issues/1682)) ([225ab82](https://www.github.com/laggingreflex/yargs/commit/225ab8271938bed3a48d23175f3d580ce8cd1306))
* tweaks to API surface based on user feedback ([#1726](https://www.github.com/laggingreflex/yargs/issues/1726)) ([4151fee](https://www.github.com/laggingreflex/yargs/commit/4151fee4c33a97d26bc40de7e623e5b0eb87e9bb))
* **usage:** single char aliases first in help ([#1574](https://www.github.com/laggingreflex/yargs/issues/1574)) ([a552990](https://www.github.com/laggingreflex/yargs/commit/a552990c120646c2d85a5c9b628e1ce92a68e797))
* **yargs-parser:** introduce single-digit boolean aliases ([#1576](https://www.github.com/laggingreflex/yargs/issues/1576)) ([3af7f04](https://www.github.com/laggingreflex/yargs/commit/3af7f04cdbfcbd4b3f432aca5144d43f21958c39))


### Bug Fixes

* __proto__ will now be replaced with ___proto___ in parse ([#1591](https://www.github.com/laggingreflex/yargs/issues/1591)) ([2474c38](https://www.github.com/laggingreflex/yargs/commit/2474c3889dcae42ddc031f0ac3872d306bf99e6b))
* add package.json to module exports ([#1818](https://www.github.com/laggingreflex/yargs/issues/1818)) ([d783a49](https://www.github.com/laggingreflex/yargs/commit/d783a49a7f21c9bbd4eec2990268f3244c4d5662)), closes [#1817](https://www.github.com/laggingreflex/yargs/issues/1817)
* address ambiguity between nargs of 1 and requiresArg ([#1572](https://www.github.com/laggingreflex/yargs/issues/1572)) ([a5edc32](https://www.github.com/laggingreflex/yargs/commit/a5edc328ecb3f90d1ba09cfe70a0040f68adf50a))
* code was not passed to process.exit ([#1742](https://www.github.com/laggingreflex/yargs/issues/1742)) ([d1a9930](https://www.github.com/laggingreflex/yargs/commit/d1a993035a2f76c138460052cf19425f9684b637))
* **deno:** get yargs working on deno@1.5.x ([#1799](https://www.github.com/laggingreflex/yargs/issues/1799)) ([cb01c98](https://www.github.com/laggingreflex/yargs/commit/cb01c98c44e30f55c2dc9434caef524ae433d9a4))
* **deno:** update types for deno ^1.4.0 ([#1772](https://www.github.com/laggingreflex/yargs/issues/1772)) ([0801752](https://www.github.com/laggingreflex/yargs/commit/080175207d281be63edf90adfe4f0568700b0bf5))
* **dependencies:** upgrade yargs-parser to fix [#1602](https://www.github.com/laggingreflex/yargs/issues/1602)  ([#1603](https://www.github.com/laggingreflex/yargs/issues/1603)) ([c67c257](https://www.github.com/laggingreflex/yargs/commit/c67c257cdf2b79af117cfd1b3938881c8f3e0677))
* **deps:** fix enumeration for normalized path arguments ([#1567](https://www.github.com/laggingreflex/yargs/issues/1567)) ([0b5b1b0](https://www.github.com/laggingreflex/yargs/commit/0b5b1b0e5f4f9baf393c48e9cc2bc85c1b67a47a))
* **docs:** describe usage of `.check()` in more detail ([932cd11](https://www.github.com/laggingreflex/yargs/commit/932cd1177e93f5cc99edfe57a4028e30717bf8fb))
* **exports:** node 13.0-13.6 require a string fallback ([#1776](https://www.github.com/laggingreflex/yargs/issues/1776)) ([b45c43a](https://www.github.com/laggingreflex/yargs/commit/b45c43a5f64b565c3794f9792150eaeec4e00b69))
* expose helpers for legacy versions of Node.js ([#1801](https://www.github.com/laggingreflex/yargs/issues/1801)) ([107deaa](https://www.github.com/laggingreflex/yargs/commit/107deaa4f68b7bc3f2386041e1f4fe0272b29c0a))
* help always displayed for the first command parsed having an async handler ([#1535](https://www.github.com/laggingreflex/yargs/issues/1535)) ([d585b30](https://www.github.com/laggingreflex/yargs/commit/d585b303a43746201b05c9c9fda94a444634df33))
* **i18n:** Japanese translation phrasing ([#1619](https://www.github.com/laggingreflex/yargs/issues/1619)) ([0894175](https://www.github.com/laggingreflex/yargs/commit/089417550ef5a5b8ce3578dd2a989191300b64cd))
* **locales:** only translate default option group name ([acc16de](https://www.github.com/laggingreflex/yargs/commit/acc16de6b846ea7332db753646a9cec76b589162))
* **locales:** remove extra space in French for 'default' ([#1564](https://www.github.com/laggingreflex/yargs/issues/1564)) ([ecfc2c4](https://www.github.com/laggingreflex/yargs/commit/ecfc2c474575c6cdbc6d273c94c13181bd1dbaa6))
* make positionals in -- count towards validation ([#1752](https://www.github.com/laggingreflex/yargs/issues/1752)) ([eb2b29d](https://www.github.com/laggingreflex/yargs/commit/eb2b29d34f1a41e0fd6c4e841960e5bfc329dc3c))
* **modules:** module path was incorrect ([#1759](https://www.github.com/laggingreflex/yargs/issues/1759)) ([95a4a0a](https://www.github.com/laggingreflex/yargs/commit/95a4a0ac573cfe158e6e4bc8c8682ebd1644a198))
* move yargs.cjs to yargs to fix Node 10 imports ([#1747](https://www.github.com/laggingreflex/yargs/issues/1747)) ([5bfb85b](https://www.github.com/laggingreflex/yargs/commit/5bfb85b33b85db8a44b5f7a700a8e4dbaf022df0))
* **positional:** positional strings no longer drop decimals ([#1761](https://www.github.com/laggingreflex/yargs/issues/1761)) ([e1a300f](https://www.github.com/laggingreflex/yargs/commit/e1a300f1293ad821c900284616337f080b207980))
* **strict mode:** report default command unknown arguments ([#1626](https://www.github.com/laggingreflex/yargs/issues/1626)) ([69f29a9](https://www.github.com/laggingreflex/yargs/commit/69f29a9cd429d4bb99481238305390107ac75b02))
* **translations:** add French translation for unknown command ([#1563](https://www.github.com/laggingreflex/yargs/issues/1563)) ([18b0b75](https://www.github.com/laggingreflex/yargs/commit/18b0b752424bf560271e670ff95a0f90c8386787))
* **translations:** fix pluralization in error messages. ([#1557](https://www.github.com/laggingreflex/yargs/issues/1557)) ([94fa38c](https://www.github.com/laggingreflex/yargs/commit/94fa38cbab8d86943e87bf41d368ed56dffa6835))
* **typescript:** yargs-parser was breaking @types/yargs ([#1745](https://www.github.com/laggingreflex/yargs/issues/1745)) ([2253284](https://www.github.com/laggingreflex/yargs/commit/2253284b233cceabd8db677b81c5bf1755eef230))
* **usage:** translate 'options' group only when displaying help ([#1600](https://www.github.com/laggingreflex/yargs/issues/1600)) ([e60b39b](https://www.github.com/laggingreflex/yargs/commit/e60b39b9d3a912c06db43f87c86ba894142b6c1c))
* **yargs:** add missing command(module) signature ([#1707](https://www.github.com/laggingreflex/yargs/issues/1707)) ([0f81024](https://www.github.com/laggingreflex/yargs/commit/0f810245494ccf13a35b7786d021b30fc95ecad5)), closes [#1704](https://www.github.com/laggingreflex/yargs/issues/1704)
* **yargs:** correct support of bundled electron apps ([#1554](https://www.github.com/laggingreflex/yargs/issues/1554)) ([a0b61ac](https://www.github.com/laggingreflex/yargs/commit/a0b61ac21e2b554aa73dbf1a66d4a7af94047c2f))


### Code Refactoring

* **ts:** ship yargs.d.ts ([#1671](https://www.github.com/laggingreflex/yargs/issues/1671)) ([c06f886](https://www.github.com/laggingreflex/yargs/commit/c06f886142ad02233db2b2ba82f2e606cbf57ccd))

## [16.2.0](https://www.github.com/yargs/yargs/compare/v16.1.1...v16.2.0) (2020-12-05)


### Features

* command() now accepts an array of modules ([f415388](https://www.github.com/yargs/yargs/commit/f415388cc454d02786c65c50dd6c7a0cf9d8b842))


### Bug Fixes

* add package.json to module exports ([#1818](https://www.github.com/yargs/yargs/issues/1818)) ([d783a49](https://www.github.com/yargs/yargs/commit/d783a49a7f21c9bbd4eec2990268f3244c4d5662)), closes [#1817](https://www.github.com/yargs/yargs/issues/1817)

### [16.1.1](https://www.github.com/yargs/yargs/compare/v16.1.0...v16.1.1) (2020-11-15)


### Bug Fixes

* expose helpers for legacy versions of Node.js ([#1801](https://www.github.com/yargs/yargs/issues/1801)) ([107deaa](https://www.github.com/yargs/yargs/commit/107deaa4f68b7bc3f2386041e1f4fe0272b29c0a))
* **deno:** get yargs working on deno@1.5.x ([#1799](https://www.github.com/yargs/yargs/issues/1799)) ([cb01c98](https://www.github.com/yargs/yargs/commit/cb01c98c44e30f55c2dc9434caef524ae433d9a4))

## [16.1.0](https://www.github.com/yargs/yargs/compare/v16.0.3...v16.1.0) (2020-10-15)


### Features

* expose hideBin helper for CJS ([#1768](https://www.github.com/yargs/yargs/issues/1768)) ([63e1173](https://www.github.com/yargs/yargs/commit/63e1173bb47dc651c151973a16ef659082a9ae66))


### Bug Fixes

* **deno:** update types for deno ^1.4.0 ([#1772](https://www.github.com/yargs/yargs/issues/1772)) ([0801752](https://www.github.com/yargs/yargs/commit/080175207d281be63edf90adfe4f0568700b0bf5))
* **exports:** node 13.0-13.6 require a string fallback ([#1776](https://www.github.com/yargs/yargs/issues/1776)) ([b45c43a](https://www.github.com/yargs/yargs/commit/b45c43a5f64b565c3794f9792150eaeec4e00b69))
* **modules:** module path was incorrect ([#1759](https://www.github.com/yargs/yargs/issues/1759)) ([95a4a0a](https://www.github.com/yargs/yargs/commit/95a4a0ac573cfe158e6e4bc8c8682ebd1644a198))
* **positional:** positional strings no longer drop decimals ([#1761](https://www.github.com/yargs/yargs/issues/1761)) ([e1a300f](https://www.github.com/yargs/yargs/commit/e1a300f1293ad821c900284616337f080b207980))
* make positionals in -- count towards validation ([#1752](https://www.github.com/yargs/yargs/issues/1752)) ([eb2b29d](https://www.github.com/yargs/yargs/commit/eb2b29d34f1a41e0fd6c4e841960e5bfc329dc3c))

### [16.0.3](https://www.github.com/yargs/yargs/compare/v16.0.2...v16.0.3) (2020-09-10)


### Bug Fixes

* move yargs.cjs to yargs to fix Node 10 imports ([#1747](https://www.github.com/yargs/yargs/issues/1747)) ([5bfb85b](https://www.github.com/yargs/yargs/commit/5bfb85b33b85db8a44b5f7a700a8e4dbaf022df0))

### [16.0.2](https://www.github.com/yargs/yargs/compare/v16.0.1...v16.0.2) (2020-09-09)


### Bug Fixes

* **typescript:** yargs-parser was breaking @types/yargs ([#1745](https://www.github.com/yargs/yargs/issues/1745)) ([2253284](https://www.github.com/yargs/yargs/commit/2253284b233cceabd8db677b81c5bf1755eef230))

### [16.0.1](https://www.github.com/yargs/yargs/compare/v16.0.0...v16.0.1) (2020-09-09)


### Bug Fixes

* code was not passed to process.exit ([#1742](https://www.github.com/yargs/yargs/issues/1742)) ([d1a9930](https://www.github.com/yargs/yargs/commit/d1a993035a2f76c138460052cf19425f9684b637))

## [16.0.0](https://www.github.com/yargs/yargs/compare/v15.4.2...v16.0.0) (2020-09-09)


### ⚠ BREAKING CHANGES

* tweaks to ESM/Deno API surface: now exports yargs function by default; getProcessArgvWithoutBin becomes hideBin; types now exported for Deno.
* find-up replaced with escalade; export map added (limits importable files in Node >= 12); yarser-parser@19.x.x (new decamelize/camelcase implementation).
* **usage:** single character aliases are now shown first in help output
* rebase helper is no longer provided on yargs instance.
* drop support for EOL Node 8 (#1686)

### Features

* adds strictOptions() ([#1738](https://www.github.com/yargs/yargs/issues/1738)) ([b215fba](https://www.github.com/yargs/yargs/commit/b215fba0ed6e124e5aad6cf22c8d5875661c63a3))
* **helpers:** rebase, Parser, applyExtends now blessed helpers ([#1733](https://www.github.com/yargs/yargs/issues/1733)) ([c7debe8](https://www.github.com/yargs/yargs/commit/c7debe8eb1e5bc6ea20b5ed68026c56e5ebec9e1))
* adds support for ESM and Deno ([#1708](https://www.github.com/yargs/yargs/issues/1708)) ([ac6d5d1](https://www.github.com/yargs/yargs/commit/ac6d5d105a75711fe703f6a39dad5181b383d6c6))
* drop support for EOL Node 8 ([#1686](https://www.github.com/yargs/yargs/issues/1686)) ([863937f](https://www.github.com/yargs/yargs/commit/863937f23c3102f804cdea78ee3097e28c7c289f))
* i18n for ESM and Deno ([#1735](https://www.github.com/yargs/yargs/issues/1735)) ([c71783a](https://www.github.com/yargs/yargs/commit/c71783a5a898a0c0e92ac501c939a3ec411ac0c1))
* tweaks to API surface based on user feedback ([#1726](https://www.github.com/yargs/yargs/issues/1726)) ([4151fee](https://www.github.com/yargs/yargs/commit/4151fee4c33a97d26bc40de7e623e5b0eb87e9bb))
* **usage:** single char aliases first in help ([#1574](https://www.github.com/yargs/yargs/issues/1574)) ([a552990](https://www.github.com/yargs/yargs/commit/a552990c120646c2d85a5c9b628e1ce92a68e797))


### Bug Fixes

* **yargs:** add missing command(module) signature ([#1707](https://www.github.com/yargs/yargs/issues/1707)) ([0f81024](https://www.github.com/yargs/yargs/commit/0f810245494ccf13a35b7786d021b30fc95ecad5)), closes [#1704](https://www.github.com/yargs/yargs/issues/1704)

[Older CHANGELOG Entries](https://github.com/yargs/yargs/blob/master/docs/CHANGELOG-historical.md)
