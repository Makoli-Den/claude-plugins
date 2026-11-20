# claude-plugins

Маркетплейс плагинов для Claude Code.

## lsp-web

Плагин подключает языковые серверы (LSP) для веб-разработки: CSS, LESS, SCSS и HTML. Благодаря им Claude Code видит ошибки и предупреждения в таких файлах, понимает структуру стилей и разметки и точнее ищет определения и использования символов. Плагин только запускает локальные серверы `vscode-css-language-server` и `vscode-html-language-server` через stdio. Он ничего не скачивает, не отправляет данные в сеть и не меняет настройки.

### Что умеет

- `.css`, `.less`, `.scss` — сервер `vscode-css-language-server`
- `.html`, `.htm` — сервер `vscode-html-language-server`

### Установка

1. Установите языковые серверы. Плагин их не ставит:

   ```
   npm install -g vscode-langservers-extracted
   ```

2. Добавьте маркетплейс и установите плагин:

   ```
   /plugin marketplace add Makoli-Den/claude-plugins
   /plugin install lsp-web@makoli-plugins
   ```

3. Выполните `/reload-plugins`. В выводе число `plugin LSP servers` должно увеличиться на 2.

### Требования

- Node.js и npm для установки серверов.
- Бинарники `vscode-css-language-server` и `vscode-html-language-server` должны быть в `PATH`. Проверка: `vscode-css-language-server --help`.

### Лицензия

MIT, см. файл `LICENSE`.
