# claude-plugins

Маркетплейс плагинов для Claude Code.

## lsp-web

Подключает языковые серверы для CSS, LESS, SCSS и HTML.

1. Установите серверы (плагин их не ставит):

   ```
   npm install -g vscode-langservers-extracted
   ```

2. Добавьте маркетплейс и установите плагин:

   ```
   /plugin marketplace add Makoli-Den/claude-plugins
   /plugin install lsp-web@makoli-plugins
   ```

Бинарники `vscode-css-language-server` и `vscode-html-language-server` должны быть в `PATH`.
