Веб-интерфейс для локального git репозитория
---------------------

* [Development](https://ya-git-dev.herokuapp.com/)
* [Production](https://ya-git-prod.herokuapp.com/)


##### Содержание
* [Node.js](#node)
* [Инфраструктура](#infrastructure)
* [Тесты](#tests)

<a name="node"><h2>Node.js</h2></a>

Для запуска необходимо указать локальный путь к репозиторию в файле server/config/config.js.

**Production**
```
npm i
npm start
```
**Development**
```
npm i
npm run dev
```
Открываем по адресу http://localhost:3000

**Технологии**
* Node + express
* Docker
* Travis CI
* Heroku
* сборка Gulp
* шаблонизатор Pug
* препроцессор SASS
* autoprefixer
* eslint, csscomb (linter)
* Babel

**Команды**
* npm run lint запускает eslint и csscomb
* npm run test запускает mocha тесты
* npm run hermione запускает hermione тесты

**Описание интерфейса**
Страницы:
* / отображает таблицу веток репозитория, ссылки на файловую структуру и коммиты ветки.
* /:branch/commit отображает коммиты в ветке
* /:branch/dir отображает файловую структуру ветки
* /dir/:hash отображает дирректорию
* /file/:hash отображает содержимое файла
На каждой странице реализована возможность выйти на уровень выше.

**Структура проекта**
Проект разбит на client, server.
Server:
* config/ - содержит конфиги( порт, хост, ссылка на репозиторий).
* controllers/ - содержит реализацию(классы) для каждой сущности (ветки, коммиты, дирректория, файл).
* helpers/ - содержит вспомогательные функции для каждой сущности (ветки, коммиты, дирректория, файл).
* routes/ - роутинг.
* utils/ - содержит вспомогательные функции, не относящиеся к конкретной сущности
* view/ - содержит шаблоны.

<a name="infrastructure"><h2>Инфраструктура</h2></a>
