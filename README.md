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

## lsp-sql

This plugin connects the `sqruff` language server for SQL. With it, Claude Code sees lint diagnostics in SQL files and can format them. The plugin only launches the local `sqruff lsp` command over stdio. It downloads nothing, sends no data over the network and changes no settings.

### Supported files

- `.sql`, `.psql`, `.pgsql` — `sqruff lsp`

### Installation

1. Install sqruff. The plugin does not install it:

   ```
   pip install sqruff
   ```

2. Add the marketplace and install the plugin:

   ```
   /plugin marketplace add Makoli-Den/claude-plugins
   /plugin install lsp-sql@makoli-plugins
   ```

3. Run `/reload-plugins`. The `plugin LSP servers` count in the output should increase by 1.

### Configuration

Set the SQL dialect in a `.sqruff` file at the project root:

```ini
[sqruff]
dialect = postgres
```

### Requirements

- Python and pip (or Cargo) to install sqruff.
- The `sqruff` binary must be on your `PATH`. Check with `sqruff --version`.

## License

MIT, see the `LICENSE` file.
