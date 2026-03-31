```markdown
![379113570-98bff411-e1e5-4de1-affe-dde8a27920f9 copy](https://github.com/user-attachments/assets/95aa1733-f495-4871-a2c1-fe4e6c0bc54f)

[8 year old girl codes with Cursor AI](https://www.youtube.com/watch?v=o5uvDZ8srHA)

В этом руководстве вы разработаете собственное веб-приложение с нуля, используя простой английский язык в различных AI-инструментах для программирования. Cursor — ведущий AI-редактор кода, способный мгновенно вносить изменения в сложные проекты с множеством файлов.

Процесс разработки быстро меняется. Вместо изучения языков программирования и фреймворков теперь важно уметь разбивать проекты на задачи, давать достаточный контекст LLM-помощникам и уметь выходить из тупиковых ситуаций. Освоив это, вы сможете запускать проекты вне своей области экспертизы — даже без команды разработчиков.

Этот шаблон React+TypeScript+Vite+MUI позволяет запускать проект локально в Cursor IDE. Замените его своей логикой и задеплойте в веб.

На прохождение этого руководства потребуется от 1 до 4 часов.

- [Идея](#idea)
- [Онлайн IDE](#online-ides)
  * [v0.dev](#v0dev)
  * [lovable.dev](#lovabledev)
  * [Bolt](#bolt)
  * [Replit Agent](#replit-agent)
  * [Claude](#claude)
- [Простое html-приложение](#a-simple-html-app)
- [React-приложение](#a-react-app)
  * [Подготовка инструментов](#get-the-tools-ready)
  * [Запуск локально](#run-locally)
  * [Внесение изменений](#make-changes)
  * [Сохранение изменений (commit)](#save-changes-commit)
  * [Деплой](#deploy)
  * [Реализация идеи](#bring-your-idea)
  * [Советы](#tips)
  * [React vs Vanilla JS](#react-vs-vanilla-js)
- [Нужен ли backend?](#do-i-need-a-backend)
  * [Добавление Firestore в проект](#adding-firestore-to-the-project)
  * [Правила](#rules)
- [Как создать Telegram-бота?](#how-to-create-a-telegram-bot)
- [Устранение неполадок](#troubleshooting)
    + [Аутентичность Git](#git-authenticity)
    + [Пустое сообщение коммита](#empty-commit-message)
    + [Первая настройка Git](#first-time-git-configuration)


# Idea

Придумайте идею веб-приложения, которое вы попробуете разработать сегодня. Можно посмотреть историю браузера, приложения в телефоне или ввести отдельные буквы в поиске ('a', 'b', 'c' и т.д.), чтобы понять, какими сайтами вы реально часто пользуетесь. Можно также загуглить "ideas for web application".

Запишите краткое описание вашего приложения в одну строку в файл — вы будете копировать этот промпт в разные инструменты для сравнения результатов. Начните с "create a web application that ...". Пока не углубляйтесь в детали — LLM умеют делать разумные предположения.

# Online IDEs

Сначала попробуем пять онлайн-инструментов: v0.dev, lovable.dev, Bolt, Replit Agent и Claude. Сначала они выглядят впечатляюще, но могут быстро разочаровать. Удачи!

## v0.dev

Перейдите на [v0.dev](https://v0.dev/) и зарегистрируйтесь. Если почта не работает — создайте аккаунт на [GitHub](https://github.com/signup) и войдите через него.

После входа вставьте вашу идею в текстовое поле.

Если первая версия совсем не работает, попросите v0 "fix" и опишите, что именно не так. Помните: LLM не видят экран так хорошо, как вы.

Если остались бесплатные запросы — поэкспериментируйте: добавляйте функции. Когда станет скучно — переходите дальше. Если не скучно — не останавливайтесь :)

Все это платные инструменты, поэтому дадут лишь несколько попыток.

## lovable.dev

Сделайте то же самое на https://lovable.dev/

## Bolt

Попробуйте https://bolt.new/: вставьте промпт в основное поле. Скорее всего, потребуется регистрация.

Если видите пустой экран:
- попробуйте Chrome вместо Firefox
- напишите в чат "I see the blank screen, please fix"
- повторите несколько раз

Бесплатные токены заканчиваются примерно после 5 запросов в день.

## Replit Agent

Попробуйте Replit Agent. Бесплатной версии нет. Напишите мне приватно за доступом.

## Claude

Попросите https://claude.ai/ создать React-приложение по вашей идее.

https://madewithclaude.com/ — можно посмотреть примеры и ремиксить.



# A simple html app

Дальше workshop про Cursor. Это более низкоуровневый инструмент — отдельная IDE, где вы будете запускать приложение локально. Но на практике он полезнее.

Перед React — потратим 10–20 минут на простой вариант: HTML-сайт в одном файле `index.html`. **Пока не клонируйте репозиторий**.

1. Установите [Cursor IDE](https://www.cursor.com/), выберите любые опции при первом запуске, затем войдите. Если уже установлен — обновите через `Cmd/Ctrl+Shift+P` → "Attempt Update".

3. Создайте пустую папку и откройте её в Cursor (`File -> Open Folder...`).

5. Нажмите `Cmd/Ctrl+I`, выберите режим **agent**. Попросите создать _simple html website_. Обязательно используйте эти слова в промпте. Вставьте свою идею.

```

Create a simple html website with easy conversion between 7 main time zones.
Time in all of theme is displayed simultaneously, and I can change hh and mm
in any of them in one click or by typing.

```

Если не получилось — создайте файл `index.html` и повторите.

Подсказка: можно перетаскивать скриншоты UI.

4. Нажмите `[Accept All]`. **Не читайте код**.

5. Откройте `index.html` в браузере:
   - `File -> Open` или `Cmd/Ctrl+O`

6. В Composer попросите изменения:

```

Make a solid-looking modern UI, draw real clock faces for each,
align them horizontally, also draw HH:MM numbers.

```

Обновите страницу.

7. Экспериментируйте с идеями.

8. Это было простое приложение. Настоящая сила Cursor — работа с большими проектами и множеством файлов.


# A React app

Теперь создадим новое приложение с использованием React, TypeScript и Vite.

Вам не обязательно понимать все концепции.

## Get the tools ready

1. Установите Node.js версии 20  
   - На Windows — не в WSL  
   - Нужна версия минимум v18  

5. Войдите в Github

## Run locally

Сделайте fork репозитория.

> Fork — это ваша копия репозитория на Github.

Клонируйте его через GitHub Desktop.

> Clone — копия на ваш компьютер.

Откройте проект в Cursor, запустите `dev` в `package.json`.

Если `npm` не найден:
- перезапустите Cursor
- попробуйте `npm run dev` вручную

## Make changes

Откройте `src/App.tsx`, нажмите `Cmd/Ctrl+I` и опишите изменения:

```

Instead of a todo list app, make an app to store and edit recipes for dishes.
Allow to recalculate number of portions for each dish.
Populate with 5 boilerplate dishes.
Make funky styling.

```

## Save changes (commit)

Напишите сообщение коммита и нажмите `[Commit]`, затем `[Sync Changes]`.

## Deploy

Запустите deploy-скрипт в `package.json`.

Если ошибки — скопируйте их в Composer и попросите `fix`.

После успеха включите GitHub Pages.

## Bring your idea

Теперь можно реализовать любую фронтенд-идею.

## Tips

- Разбивайте задачи на маленькие части  
- Часто делайте commit  
- Используйте Composer, не Chat  
- При ошибках — откатывайтесь или просите fix  
- Используйте debug вывод  
- Добавляйте скриншоты  
- Используйте @Codebase, @Docs, @Web  

## React vs Vanilla JS

React лучше масштабируется и управляет сложностью.  
LLM помогают, но важна точность промптов и структура приложения.



# Do I need a backend?

Для хранения данных — local storage.

Для синхронизации — Firestore.

Для авторизации — Firebase Authentication.

Для логики — Firebase Cloud Functions.

## Adding Firestore to the project

1. Попросите Cursor:

```

Save data to Firestore

````

Запустите установку `firebase` вручную.

2. Войдите в Firebase  
3. Создайте проект  
4. Создайте Firestore в test mode  
6. Добавьте web app  
7. Вставьте `firebaseConfig` в код  

```js
const firebaseConfig = {
  apiKey: "YOU_SHOULD_GET_THIS_KEY_AT_THE_PREVIOUS_STEP",
  authDomain: "your-app-43gh9.firebaseapp.com",
  projectId: "your-app-43gh9",
  storageBucket: "your-app-43gh9.appspot.com",
  messagingSenderId: "783999999999",
  appId: "1:783553619737:web:dff6fce9589deaf34",
  measurementId: "G-JL7GNDPV6V"
};
````

## Rules

Если не включили test mode — настройте правила:

```yaml
rules_version = '2';

service cloud.firestore {
  match /databases/{database}/documents {
    match /{document=**} {
      allow read, write: if true;
    }
  }
}
```

⚠️ Это открывает доступ всем.

# How to create a Telegram bot?

1. Создайте папку
2. Откройте в Cursor
3. `Cmd/Ctrl+I` → `create a simple telegram bot`

   * следуйте инструкциям
   * используйте `pip3` и `python3` при необходимости
   * перезапускайте скрипт после изменений

# Troubleshooting

Если возникли проблемы — отправьте скриншоты автору.

### Git authenticity

Введите `yes`.

### Empty commit message

Введите `fix` в `COMMIT_EDITMSG`.

### First time Git configuration

Введите:

```
git config --global user.email "YOUR_EMAIL@gmail.com"
```

```
git config --global user.name "JANE DOE"
```

```
```
