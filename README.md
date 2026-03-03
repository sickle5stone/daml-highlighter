# Daml Syntax Highlighter

Syntax highlighting for [Daml](https://www.digitalasset.com/developers) files in VS Code. No SDK, no language server, no dependencies. Just colors.

![Daml highlighting example](https://raw.githubusercontent.com/sickle5stone/daml-highlighter/main/screenshot.png)

## What it highlights

- Keywords: `template`, `choice`, `controller`, `signatory`, `observer`, `ensure`, `with`, `do`, `let`, `where`
- Types: `Party`, `Decimal`, `Text`, `Bool`, `Time`, `Optional`, `ContractId`, plus any uppercase identifier
- Actions: `create`, `fetch`, `exercise`, `submit`, `archive`, `assertMsg`, `getTime`
- Data declarations: `data`, `type`, `class`, `instance`, `deriving`, `interface`
- Comments: line (`--`), doc (`-- |`), nested block (`{- -}`)
- Strings, numbers (including `1_000_000.0`), and operators (`->`, `<-`, `>>=`, `<>`)

## Install

**From the Marketplace:** Search "Daml Syntax Highlighter" in the Extensions panel.

**From VSIX:**
```
code --install-extension daml-highlighter-0.1.0.vsix
```

## When to use this vs. the official Daml extension

The [official Digital Asset extension](https://marketplace.visualstudio.com/items?itemName=DigitalAssetHoldingsLLC.daml) bundles a language server, build tools, and SDK integration. It requires the Daml SDK installed on your machine.

This extension does one thing: highlight `.daml` files. Use it if you want to read or review Daml code without installing the SDK, or if you find the official extension too heavy for your workflow.

If you have the official extension installed, disable it or this one. Running both will cause conflicts since they register the same language ID.

## Supported tokens

The grammar covers Daml's Haskell-derived syntax. User-defined types (anything starting with an uppercase letter) are highlighted automatically. Daml-specific constructs like `template`, `choice`, `signatory`, `controller` get their own scope so themes can color them distinctly.

Nested block comments (`{- outer {- inner -} still a comment -}`) are handled correctly.

## Contributing

Found a token that's not highlighted? Open an issue or PR on [GitHub](https://github.com/sickle5stone/daml-highlighter). The grammar lives in `syntaxes/daml.tmLanguage.json`.

## License

Apache-2.0
