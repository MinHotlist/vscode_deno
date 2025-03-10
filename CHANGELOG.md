# Change Log

Releases of the extension can be downloaded from
[Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=denoland.vscode-deno).

### [3.8.0](https://github.com/denoland/vscode_deno/compare/3.7.0...3.8.0) / 2021.08.10

- feat: add ability to set cache directory in settings (#477)

  The plugin supports setting the `deno.cache` option, which allows setting a
  specific cache directory for the Deno language server to use. This is similar
  to the `DENO_DIR` environment variable that can be set when invoking Deno on
  the command line.

- feat: hide the status bar unless `deno.enable` is true (#485)

  The Deno language server runs in a workspace even when the project isn't
  enabled for Deno, as the formatting services are still available and the
  language server needs to keep track of the state of documents in case the
  workspace does become enabled. It is confusing to see the version of Deno in
  the status bar. The extension now will not display this information unless the
  workspace is enabled for Deno.

- fix: properly handle plugin configuration at startup (#474)

  This led to an issue where if Deno started before the built in TypeScript
  language service in a Deno enabled project, the TypeScript language service
  diagnostics were not _muted_ and incorrect or duplicate diagnostics were being
  displayed.

### [3.7.0](https://github.com/denoland/vscode_deno/compare/3.6.1...3.7.0) / 2021.07.02

- feat: add support for import map in test code lens (#446)

  When using the test code lens, the configuration of the import map is
  reflected in running the test.

- fix: activate extension on markdown / json / jsonc (#447)
- fix: setting then clearing "deno.path" config should not use empty string for
  path (#452)
- fix: better handling when language server fails to start (#454)

### [3.6.1](https://github.com/denoland/vscode_deno/compare/3.6.0...3.6.1) / 2021.06.08

- fix: update packaging and pin vsce version (#440)

### [3.6.0](https://github.com/denoland/vscode_deno/compare/3.5.1...3.6.0) / 2021.06.08

- feat: add support for tasks and test code lens (#436)

  The Deno Language Server as of Deno 1.11, code lenses for test are sent to the
  client, and the extension now supports allowing those tests to be run in the
  IDE. In addition, several tasks have been added to the extension which allow
  users to setup and configure common Deno CLI tasks via the `tasks.json`.
  Checkout out the [testing](./docs/testing.md) and [tasks](./docs/tasks.md)
  documentation for more information.

### [3.5.1](https://github.com/denoland/vscode_deno/compare/3.5.0...3.5.1) / 2021.06.02

- fix: bump semver of extension (#429)

  This informs users that they require Deno 1.10.3 or later for the extension to
  properly work.

### [3.5.0](https://github.com/denoland/vscode_deno/compare/3.4.0...3.5.0) / 2021.06.01

- feat: recognize JSON(C) and markdown files (#404)

  This allows the Deno language server to be used as a formatter for JSON(C) and
  markdown files.

### [3.4.0](https://github.com/denoland/vscode_deno/compare/3.3.0...3.4.0) / 2021.05.11

- feat: handle per resource configuration (#411)

  Along with Deno v1.10, the extension now supports vscode's multi-root
  workspaces, which will allow you to enable and disable Deno per workspace
  folder.

- feat: add `internalDebug` config flag (#406)

  Enabling `deno.internalDebug` to `true` will output additional (quite verbose)
  logging information to help with diagnosing language server issues. This
  requires Deno v1.10 or later to work.

- fix: activate on `reloadImportRegistries` command (#407)
- docs: fix type in `ImportCompletions.md` (#410)

### [3.3.0](https://github.com/denoland/vscode_deno/compare/3.2.0...3.3.0) / 2021.04.13

- feat: add support for import registry completions (#380)
- feat: add restart language server command (#385)
- feat: add version notification message (#383)
- feat: support for relative path resolution (using workspaces) in deno.path
  (#381)

### [3.2.0](https://github.com/denoland/vscode_deno/compare/3.1.0...3.2.0) / 2021.03.15

- feat: read-add debug support (#351)
- feat: add settings to affect completions (#368)
- fix: manual `deno` command resolution on windows (#367)

### [3.1.0](https://github.com/denoland/vscode_deno/compare/3.0.1...3.1.0) / 2021.03.02

- feat: add deno.path setting (#350)
- fix: activate extension on command (#336)
- chore: move Releases.md to CHANGELOG.md for better marketplace integration
  (#344)
- docs: recommend import_map.json instead of import-map.json (#340)

### [3.0.1](https://github.com/denoland/vscode_deno/compare/3.0.0...3.0.1) / 2021.02.19

- fix: EXTENSION_ID corrected to denoland.vscode-deno extension (#333)

### [3.0.0](https://github.com/denoland/vscode_deno/compare/canary/0.0.10...3.0.0) / 2021.02.19

Canary has been released as the main extension. Use Deno 1.7.5 or later.

- chore: README improvements (#331)
- feat: use preview instead of display for status (#330)
- feat: add a welcome screen for extension (#329)
- fix: typo in init command (#327)

### [canary/0.0.10](https://github.com/denoland/vscode_deno/compare/canary/0.0.9...canary/0.0.10) / 2021.02.13

- fix: don't remove required files when packaging vsix

### [canary/0.0.9](https://github.com/denoland/vscode_deno/compare/canary/0.0.8...canary/0.0.9) / 2021.02.13

- feat: add initialize workspace command (#316)
- feat: support deno cache quick fix (#322)
- feat: add implementations code lens configuration option (#319)
- chore: add screenshot to README (#323)

### [canary/0.0.8](https://github.com/denoland/vscode_deno/compare/canary/0.0.7...canary/0.0.8) / 2021.02.01

- feat: code lens for references (#308)
- feat: disable most of builtin language service when deno enabled (#307)

### [canary/0.0.7](https://github.com/denoland/vscode_deno/compare/canary/0.0.6...canary/0.0.7) / 2021.01.24

- feat: add back JSON schema for import maps (#283)
- feat: add deno cache command (#291)
- feat: plugin ignores getImplementation requests when Deno enabled (#302)
- feat: change textDocument/rename to use LSP (#292)
- fix: pass NO_COLOR when starting lsp (#293)

### [canary/0.0.6](https://github.com/denoland/vscode_deno/compare/canary/0.0.5...canary/0.0.6) / 2020.12.13

- fix: include typescript-deno-plugin in vsix (#285)

### [canary/0.0.5](https://github.com/denoland/vscode_deno/compare/canary/0.0.4...canary/0.0.5) / 2020.12.09

- chore: release on canary/* tag

### [canary/0.0.4](https://github.com/denoland/vscode_deno/compare/canary/0.0.3...canary/0.0.4) / 2020.12.09

- chore: disable built in completions (#279)

### [canary/0.0.3](https://github.com/denoland/vscode_deno/compare/v3.0.0-pre.1...canary/0.0.3) / 2020.12.08

- feat: suppresses quick info and document highlights (#266)
- feat: suppress references and definitions (#270)
- feat: extension activates on deno virtual files (#275)
- fix: Update version so it can be published on marketplace (#272)
- fix: plugin settings match language server settings (#276)

### [v3.0.0-pre.1](https://github.com/denoland/vscode_deno/compare/v2.3.3...v3.0.0-pre.1) / 2020.11.30

This is a full rewrite of the extension to use the upcoming `deno lsp` feature.

### [v2.3.3](https://github.com/denoland/vscode_deno/compare/v2.3.2...v2.3.3) / 2020.11.05

- chore: update compilation settings to match 1.5 (#251)

### [v2.3.2](https://github.com/denoland/vscode_deno/compare/v2.3.1...v2.3.2) / 2020.10.12

- chore: disable importsNotUsedAsValues --unstable default (#240)
- build: husky pre-commit hooks (#224)

### [v2.3.1](https://github.com/denoland/vscode_deno/compare/v2.3.0...v2.3.1) / 2020.09.24

- fix: enable recursive mode for mkdir of cache path (#232)

### [v2.3.0](https://github.com/denoland/vscode_deno/compare/v2.2.3...v2.3.0) / 2020.09.24

- feat: generic import intellisense (#219)
- feat: out of the box debug support (#221)
- feat: init project command to quickly set up .vscode/settings.json (#207)
- fix: `Fetch the module` quickfix does not respect deno.unstable setting (#213)
- chore: fix manual URL in hover card (#226)

### [v2.2.3](https://github.com/denoland/vscode_deno/compare/v2.2.2...v2.2.3) / 2020.09.13

- fix: failed to load typescript-deno-plugin error (#205)
- chore: align ignored diagnostics to Deno 1.4.0 (#205)

### [v2.2.2](https://github.com/denoland/vscode_deno/compare/v2.2.1...v2.2.2) / 2020.09.13

- chore: update tsconfig to match Deno 1.4.0 (#204)

### [v2.2.1](https://github.com/denoland/vscode_deno/compare/v2.2.0...v2.2.1) / 2020.09.09

- fix: remove ansi codes from install output (#185)
- fix: deno.land/x cache will always renew on vscode restart after 24 hours
  (#191)
- fix: ignore 'rule' for this line does not work on the first line (#192)
- build: release .vsix artifact during release (#195)

### [v2.2.0](https://github.com/denoland/vscode_deno/compare/v2.1.2...v2.2.0) / 2020.09.07

- feat: add inline `deno lint` diagnostics (#162)
- fix: add IntelliSense support for `export` (#184)
- refactor: move imports IntelliSense logic to server (#181)

### [v2.1.2](https://github.com/denoland/vscode_deno/compare/v2.1.1...v2.1.2) / 2020.09.04

- fix: another typescript not found error (#178)

### [v2.1.1](https://github.com/denoland/vscode_deno/compare/v2.1.0...v2.1.1) / 2020.09.04

- fix: typescript not found error (#177)

### [v2.1.0](https://github.com/denoland/vscode_deno/compare/v2.0.16...v2.1.0) / 2020.09.04

- feat: IntelliSense support for std and deno.land/x imports (#172)
- fix: add support for URLs with non default ports (#173)
- fix: correctly handle non existing \$DENO_DIR/deps (#169)
- refactor: simplify import map json validation (#167)
- chore: update dependencies (#165)
- docs: remove non english readme (#164)

### [v2.0.16](https://github.com/denoland/vscode_deno/compare/v2.0.15...v2.0.16) / 2020.08.29

- fix: autocomplete supports adding extensions (#156)
- docs: fix readme install description (#160)

### [v2.0.15](https://github.com/denoland/vscode_deno/compare/v2.0.14...v2.0.15) / 2020.08.28

- build: fix releasing extension to Visual Studio Marketplace from CI (#159)

### [v2.0.14](https://github.com/denoland/vscode_deno/compare/v2.0.13...v2.0.14) / 2020.08.25

- fix: fixActions not import Deno module URL correctly (#154)

### [v2.0.11-v2.0.13](https://github.com/denoland/vscode_deno/compare/v2.0.10...v2.0.13) / 2020.08.14

- fix: use the correct `typescript-deno-plugin` (#144)
- docs: update contributing instructions (#146)

### v2.0.0-v2.0.10 / 2020.08.13

Replacement of extension by the one written by @axetroy.

### v1.x / June 2020 - July 2020

Initial release of the extension originally written by @justjavac.
