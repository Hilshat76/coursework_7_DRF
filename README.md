Для проверки созданы фикстуры user_data.json с пользователями (в т.ч. и админ) и habits.json с привычками.
Для проверки необходимо присвоить пользователям Telegram-ID либо Telegram-username, а также создать telegram_bot и совзаимодейтвовать Telegram-username с ботом.


# Курсовая работа 7. DRF.

## Контекст

В 2018 году Джеймс Клир написал книгу «Атомные привычки», которая посвящена приобретению новых полезных привычек и искоренению старых плохих привычек. Заказчик прочитал книгу, впечатлился и обратился к вам с запросом реализовать трекер полезных привычек.

В рамках учебного курсового проекта реализуйте бэкенд-часть SPA веб-приложения.

## Критерии приемки курсовой работы

* Настроили CORS.
* Настроили интеграцию с Телеграмом.
* Реализовали пагинацию.
* Использовали переменные окружения.
* Все необходимые модели описаны или переопределены.
* Все необходимые эндпоинты реализовали.
* Настроили все необходимые валидаторы.
* Описанные права доступа заложены.
* Настроили отложенную задачу через Celery.
* Проект покрыли тестами как минимум на 80%.
* Код оформили в соответствии с лучшими практиками.
* Имеется список зависимостей.
* Результат проверки Flake8 равен 100%, при исключении миграций.
* Решение выложили на GitHub.

## Задание 1

Подключить и настроить вывод документации для проекта. Убедиться, что каждый из реализованных эндпоинтов описан в документации верно, при необходимости описать вручную.

_Для работы с документацией проекта воспользуйтесь библиотекой drf-yasg или drf-spectacular._

_Как вручную можно сформировать документацию в drf-yasg можно почитать https://drf-yasg.readthedocs.io/en/stable/custom_spec.html, в drf-spectacular — https://habr.com/ru/articles/733942/ или https://drf-spectacular.readthedocs.io/en/latest/customization.html._

## Задание 2

Подключить возможность оплаты курсов через https://stripe.com/docs/api.

Доступы можно получить напрямую из документации, а также пройти простую регистрацию по адресу https://dashboard.stripe.com/register.

_Для работы с учебным проектом достаточно зарегистрировать аккаунт и не подтверждать его — аккаунт будет находиться в тестовом режиме._

Для работы с запросами вам понадобится реализовать обращение к эндпоинтам:

* https://stripe.com/docs/api/products/create — создание продукта;
* https://stripe.com/docs/api/prices/create — создание цены;
* https://stripe.com/docs/api/checkout/sessions/create — создание сессии для получения ссылки на оплату.

_При создании цены и сессии обратите внимание на поля, которые вы передаете в запросе. Внимательно изучите значение каждого поля и проанализируйте ошибки при их возникновении, чтобы создать корректную запись._

_При создании сессии нужно передавать id цены, которая соответствует конкретному продукту._

Для тестирования можно использовать номера карт из документации:

* https://stripe.com/docs/terminal/references/testing#standard-test-cards.

#### _Примечание_

_Подключение оплаты лучше всего рассматривать как обычную задачу подключения к стороннему API._

_Основной путь: запрос на покупку → оплата. Статус проверять не нужно._

_Каждый эквайринг предоставляет тестовые карты для работы с виртуальными деньгами._

## * Дополнительное задание

Реализуйте проверку статуса с помощью эндпоинта https://stripe.com/docs/api/checkout/sessions/retrieve — получение данных о сессии по идентификатору.
