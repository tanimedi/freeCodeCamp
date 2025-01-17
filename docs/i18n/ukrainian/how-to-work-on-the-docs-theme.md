# How to Work on Documentation

## Work on the Content of the Docs

Щоб працювати над рекомендаціями щодо внеску, ви можете редагувати або додавати файли в каталозі `docs`, [доступному тут](https://github.com/freeCodeCamp/freeCodeCamp/tree/main/docs). Коли ваші зміни об’єднані, вони будуть автоматично доступними на документаційному сайті.

Подумайте, чи потрібно додавати файл до бічної панелі навігації, коли додаєте новий файл до каталогу `docs`. Зазвичай ми створюємо посилання у файлі [`_sidebar.md`](_sidebar.md) для нових та незалежних посібників. Крім того, ви можете дотримуватись наведених нижче інструкцій для створення внутрішнього посилання для допоміжних посібників.

### How to Create an Internal Link

Якщо ви хочете створити внутрішнє посилання, націлене на інший розділ рекомендацій щодо внеску, використовуйте цей формат:

```md
[Link text](target-file-name.md#target-section-heading-id)

// Якщо цільовий розділ знаходиться на тій же сторінці, ви можете опустити назву файлу
[Link text](#target-section-heading-id)
```

Не забудьте додати розширення файлу (`.md`). Не вказуйте повну URL-адресу та не додавайте `/` перед назвою файлу.

Це важливо для того, щоб посилання працювали для перекладеної версії документа. В іншому випадку вони перенаправлятимуть на англійську версію сторінки, незалежно від мови.

#### Переклад документації з внутрішніми посиланнями

Коли ви працюєте над перекладом документації на Crowdin, не забудьте змінити `#target-section-heading-id` на ідентифікацію в перекладеному документі. [Дізнатись більше про переклад документації](how-to-translate-files.md#translate-documentation).

## Work on the Docs Theme

> [!NOTE] Коротке нагадування, що вам не потрібно нічого налаштовувати для роботи над вмістом документації.
> 
> Щоб працювати над рекомендаціями щодо внеску, див. [робота над вмістом документації](#work-on-the-docs-content).

### Structure of the Docs Website

Сайт створений з використанням [`docsify`](https://docsify.js.org) та обслуговується завдяки GitHub Pages.

Зазвичай вам не потрібно буде змінювати конфігурації або створювати сайт локально. Якщо ви зацікавлені, це працює ось так:

- Джерело домашньої сторінки для цього сайту доступне в [`docs/index.html`](index.html).
- Ми обслуговуємо цей файл як SPA, використовуючи `docsify` та GitHub Pages.
- Скрипт `docsify` генерує вміст файлів `markdown` в каталозі `docs` за запитом.
- Домашня сторінка генерується з [`_coverpage.md`](_coverpage.md).
- Бічна панель навігації генерується з [`_sidebar.md`](_sidebar.md).

### Serving the Documentation Site Locally

Install freeCodeCamp locally ([see the local setup guide](how-to-setup-freecodecamp-locally)), we bundled the CLI with the development tools so you can run the command below as needed from the root of the repo:

#### Serve and Launch the Documentation Site

```console
pnpm run docs:serve
```

> Сайт документації повинен бути доступним на <http://localhost:3400>
