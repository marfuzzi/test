####Cервис бронирования переговорок.

Решение тестового задания №3 шестой [Школы разработки интерфейсов](https://academy.yandex.ru/events/frontend/shri_msk-2018).

## Запуск

### Production
```
npm i
npm run build
npm run start-prod
```

Открываем по адресу http://localhost:5050

### Development

#### Запуск приложения
```npm run start```
Приложение запустится по адресу http://localhost:5000

#### Запуск graphql server'а
1. открываем новое окно терминала
2. Обновляем данные:
```
cd server
rm -f db.sqlite3
node create-mock-data.js
```
3. Запускаем сервер:
```
nodemon index.js
```
Слушаем сервер на http://localhost:5050

**Технологии**
* React
* Redux
* Appolo Graphql

**Библиотеки**
* moment
* lodash

### Описание интерфейса
**Главная страница**
* На главной странице отображены список переговорок, встречи, календарь, текущее время, кнопка создания встречи.
* Календарь динамичен. Синим цветом выделен текущий день. На события других дней можно переключиться с помощью стрелок или выбором даты в календаре. Таким образом будет отображен выбранный день. Линия текущего времени исчезнет.
* При наведении на свободный слот отображается тултип. При нажатии переходим на страницу создания новой встречи.
* При наведении на событие появляется тултип с информацией о встрече. (Не реализовано: тултип выходит на границы поля встреч.)
* При клике на правую верхнюю кнопку тултипа переходим на страницу редактирования встречи.
**Страница создания встречи**
* Страница создания встречи
* Реализована валидация. Кнопка создания разблокируется при заполнении всех форм.
Поля времени и участников не вводятся, а выбираются из списка.
* Реализован выпадающий календарь на месяц. Можно ввести дату, можно выбрать на календаре.
* При создании встречи осуществлен переход на день ее создания. Пользователь увидит отображение встречи в сетке.
* Реализована функция подбора рекомендуемых переговорок
**Страница редактирования встречи**
* При удалении текущей переговорки, появляются рекомендованные(по алгоритму) или дополнительная информация.
* Удалить - удаляет встречу, и осуществляет переход на главную страницу.
* Редактировать - редактирует текущую встречу.
**Функция getRecommendation**
* Алгоритм функции с описанием ./utils/getRecommendation.js
