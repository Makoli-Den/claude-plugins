# claude-plugins

A plugin marketplace for Claude Code.

## lsp-web

This plugin connects language servers (LSP) for web development: CSS, LESS, SCSS and HTML. With them, Claude Code sees errors and warnings in such files, understands the structure of stylesheets and markup, and finds symbol definitions and usages more accurately. The plugin only launches the local `vscode-css-language-server` and `vscode-html-language-server` servers over stdio. It downloads nothing, sends no data over the network and changes no settings.

### Supported files

- `.css`, `.less`, `.scss` — `vscode-css-language-server`
- `.html`, `.htm` — `vscode-html-language-server`

### Installation

1. Install the language servers. The plugin does not install them:

   ```
   npm install -g vscode-langservers-extracted
   ```

2. Add the marketplace and install the plugin:

   ```
   /plugin marketplace add Makoli-Den/claude-plugins
   /plugin install lsp-web@makoli-plugins
   ```

3. Run `/reload-plugins`. The `plugin LSP servers` count in the output should increase by 2.

### Requirements

- Node.js and npm to install the servers.
- The `vscode-css-language-server` and `vscode-html-language-server` binaries must be on your `PATH`. Check with `vscode-css-language-server --help`.

### License

MIT, see the `LICENSE` file.
