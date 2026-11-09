# Zed MDX

MDX support for [Zed](https://zed.dev): syntax highlighting plus a language server.

- **Highlighting:** tree-sitter grammar ([humanfriend22/tree-sitter-mdx](https://github.com/humanfriend22/tree-sitter-mdx)) with queries for highlighting, injections, indents, outline and text objects. Markdown inside JSX wrapper elements (e.g. `<Layout>…</Layout>`) is highlighted via a markdown injection, and capitalized JSX components are highlighted as types.
- **Language server:** [mdx-analyzer](https://github.com/mdx-js/mdx-analyzer). It needs the TypeScript JS API, which TypeScript 7 no longer ships, so the extension installs [`@typescript/typescript6`](https://www.npmjs.com/package/@typescript/typescript6) for it.
- **TypeScript plugin:** [@mdx-js/typescript-plugin](https://github.com/mdx-js/mdx-analyzer/tree/main/packages/typescript-plugin) is registered with `vtsls` and `typescript-language-server` so `.ts`/`.tsx` files understand `.mdx` imports.

## TypeScript configuration

TypeScript features (hover, go-to-definition, type errors) are enabled by default. To disable them, add to Zed's `settings.json`:

```json
"lsp": {
    "mdx-analyzer": {
        "initialization_options": {
            "typescript": {
                "enabled": false
            }
        }
    }
}
```

## Development

`zed: install dev extension` and select this folder.
