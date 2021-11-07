# free-omnisharp-vscode

The debugger included in the official C# extension is [proprietary](https://aka.ms/VSCode-DotNet-DbgLicense) and is licensed to only work with Microsoft versions of vscode.
This extension replaces it with [Samsung's MIT-licensed alternative](https://github.com/Samsung/netcoredbg/blob/master/LICENSE).

## Installation

This extension is published at [open-vsx.org](https://open-vsx.org/extension/muhammad-sammy/csharp).

### Build from source

Requirements:

- [nodejs](https://nodejs.org)
- npm (comes with nodejs)

```bash
git clone https://github.com/muhammadsammy/free-omnisharp-vscode.git

cd free-omnisharp-vscode

npm install

npx gulp 'vsix:release:package'

```

then run `Extensions: Install from VSIX` from the command pallete and select the `csharp-VERSION_NUMBER.vsix` file.

# From [OmniSharp/omnisharp-vscode](https://github.com/OmniSharp/omnisharp-vscode) README

## Note about using .NET Core 3.1.40x SDKs

The .NET 3.1.40x SDKs require version 16.7 of MSBuild.

For MacOS and Linux users who have Mono installed, this means you will need to set `omnisharp.useGlobalMono` to `never` until a version of Mono ships with MSBuild 16.7.

## Note about using .NET 5 SDKs

The .NET 5 SDK requires version 16.8 of MSBuild.

For Windows users who have Visual Studio installed, this means you will need to be on the latest Visual Studio 16.8 Preview.
For MacOS and Linux users who have Mono installed, this means you will need to set `omnisharp.useGlobalMono` to `never` until a version of Mono ships with MSBuild 16.8.

## What's new in 1.23.17
* Greatly improved download experience: when the C# extension is downloaded from the VS Code Marketplace, it will include all of its dependencies already ([#4775](https://github.com/OmniSharp/omnisharp-vscode/issues/4775))
* Fix decompilation authorization check ([#4817](https://github.com/OmniSharp/omnisharp-vscode/issues/4817), PR: [#4821](https://github.com/OmniSharp/omnisharp-vscode/pull/4821))
* Fix typo in Readme.md (PR: [#4819](https://github.com/OmniSharp/omnisharp-vscode/pull/4819))
* Fix indentation level and spacing for xUnit fact snippet. (PR: [#4831](https://github.com/OmniSharp/omnisharp-vscode/pull/4831))
* Support relative paths with omnisharp.testRunSettings (PR: [#4860](https://github.com/OmniSharp/omnisharp-vscode/pull/4860)) (PR: [#4849](https://github.com/OmniSharp/omnisharp-vscode/pull/4849))
* Add `CimAttachItemsProvider` to replace `WmicAttachItemsProvider` (PR: [#4848](https://github.com/OmniSharp/omnisharp-vscode/pull/4848))       
* Enhance sourceFileMap documentation (PR: [#4844](https://github.com/OmniSharp/omnisharp-vscode/pull/4844))
* Update the indentation level and spacing for the '"xUnit Test" fact' snippet. (PR: [#4831](https://github.com/OmniSharp/omnisharp-vscode/pull/4831))

* Debugger changes:
  * The debugger itself runs on .NET 6 RC2
  * Enhanced support for launchSettings.json ([#3121](https://github.com/OmniSharp/omnisharp-vscode/issues/3121))
  * Fixed process listing on Windows 11 (PR: [#4848](https://github.com/OmniSharp/omnisharp-vscode/pull/4848)) _(Many thanks to [@eternalphane](https://github.com/eternalphane))_
  * Update debugger to 1.23.17 (PR: [#4855](https://github.com/OmniSharp/omnisharp-vscode/pull/4855))
  * Update Debugger Labels (PR: [#4798](https://github.com/OmniSharp/omnisharp-vscode/pull/4798))
  * Add Debug Welcome View (PR: [#4797](https://github.com/OmniSharp/omnisharp-vscode/pull/4797))

* Update OmniSharp version to 1.37.17:
  * Update versions to match dotnet SDK 6.0.1xx (PR: [omnisharp-roslyn#2262](https://github.com/OmniSharp/omnisharp-roslyn/pull/2262))
  * Remove all completion commit characters in suggestion mode. ([omnisharp-roslyn#1974](https://github.com/OmniSharp/omnisharp-vscode/issues/1974), [omnisharp-roslyn#3219](https://github.com/OmniSharp/omnisharp-vscode/issues/3219), [omnisharp-roslyn#3647](https://github.com/OmniSharp/omnisharp-vscode/issues/3647), [omnisharp-roslyn#4833](https://github.com/OmniSharp/omnisharp-vscode/issues/4833), PR: [omnisharp-roslyn#2253](https://github.com/OmniSharp/omnisharp-roslyn/pull/2253))
  * fixed logging interpolation in ProjectManager (PR: [omnisharp-roslyn#2246](https://github.com/OmniSharp/omnisharp-roslyn/pull/2246))
  * Support signature help for implicit object creation ([omnisharp-roslyn#2243](https://github.com/OmniSharp/omnisharp-roslyn/issues/2243), PR: [omnisharp-roslyn#2244](https://github.com/OmniSharp/omnisharp-roslyn/pull/2244))
  * Implement /v2/gotodefinition for Cake ([omnisharp-roslyn#2209](https://github.com/OmniSharp/omnisharp-roslyn/issues/2209), PR: [omnisharp-roslyn#2212](https://github.com/OmniSharp/omnisharp-roslyn/pull/2212))

### Emmet support in Razor files

To enable emmet support, add the following to your settings.json:

```json
"emmet.includeLanguages": {
    "aspnetcorerazor": "html"
}
```

### Semantic Highlighting

The C# semantic highlighting support is in preview. To enable, set `editor.semanticHighlighting.enabled` and `csharp.semanticHighlighting.enabled` to `true` in your settings. Semantic highlighting is only provided for code files that are part of the active project.

To really see the difference, try the new Visual Studio 2019 Light and Dark themes with semantic colors that closely match Visual Studio 2019.

### Development

First install:

- Node.js (8.11.1 or later)
- Npm (5.6.0 or later)

To **run and develop** do the following:

- Run `npm i`
- Run `npm run compile`
- Open in Visual Studio Code (`code .`)
- _Optional:_ run `npm run watch`, make code changes
- Press <kbd>F5</kbd> to debug

To **test** do the following: `npm run test` or <kbd>F5</kbd> in VS Code with the "Launch Tests" debug configuration.

To **package** an extension file for installation do the following:

- Run `npm install –g vsce` to install a tool for composing an extension file
- Run `vsce package` to package an extension file using the tool 
