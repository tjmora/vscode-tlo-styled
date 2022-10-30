# vscode-tlo-styled

This extension is available at the [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=tjmora.vscode-tlo-styled).

Syntax highlighting and IntelliSense for [TLO.styled](https://github.com/tjmora/template-literal-object).

Uses a CSS grammar built on top of [language-sass](https://github.com/atom/language-sass) and [language-css](https://github.com/atom/language-css).

## Install

Inside VSCode, press `Ctrl+P`, and enter:

```
ext install vscode-tlo-styled
```

It should be the top result.

## Features

- Syntax highlighting for styled components in JavaScript and TypeScript.
- Detailed CSS IntelliSense while working in styled strings.
- Syntax error reporting.

## Usage

The styled-components extension adds highlighting and IntelliSense for the template literal objects as set by TLO.styled static method in JavaScript and TypeScript. See [plugin configuration](https://github.com/Microsoft/typescript-styled-plugin#configuration) for information on configuring the linter and other language features.

## Contributing

This is a co-updating fork of [vscode-styled-components](https://github.com/styled-components/vscode-styled-components). 
Any contribution, except when dealing directly with template literal objects, must be made there. 
[See their contributions policy](https://github.com/styled-components/vscode-styled-components/blob/master/CONTRIBUTING.md).

## Troubleshooting

### There's no syntax highlighting?

Syntax Highlighting is specifically made to work with `TLO.styled`, not `TLO.set`, and certainly 
not for styled-components (Use the [vscode-styled-components](https://marketplace.visualstudio.com/items?itemName=styled-components.vscode-styled-components) 
extension for that).

Secondly make sure your file is set to the right language. It should be `typescriptreact` or `javascriptreact`. Using the correct extensions (jsx, tsx) should help with this.

### Emmet tab completion isn't working

Be sure to include `"emmet.triggerExpansionOnTab": true` in your VSCode settings to enable tab completion.\*\* More settings and instructions can be found [here](https://code.visualstudio.com/docs/editor/emmet).

### Emmet is auto completing HTML tags instead of CSS

This is an upstream issue in VSCode unfortunately. The root cause is here: https://github.com/microsoft/vscode/issues/119736 which itself was raised from https://github.com/microsoft/vscode/issues/51537. There was an [issue raised](https://github.com/styled-components/vscode-styled-components/issues/191) in this repo but there's nothing that can be done on our end.

### I get "unknown property: X" on a property I know is valid

Property look up comes from the [css language service](https://github.com/microsoft/vscode-css-languageservice) which in turn comes from [MDN Data](https://github.com/mdn/data). If its a custom property, or something that is not in MDN you can add your own property like so: https://github.com/microsoft/typescript-styled-plugin/issues/58#issuecomment-444733368

If however you believe this property is standard and thus missing you can raise this issue with either one of the above projects; please check for any raised issue first.
