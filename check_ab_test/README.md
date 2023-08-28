# Оценка результатов внедрения изменений в рекомендательной системе

## Цель исследования:

Провести оценку результатов A/B-теста внедрения улучшений рекомендательной системы.

## Использованные данные:

`ab_project_marketing_events.csv` — календарь маркетинговых событий на 2020 год.

- название маркетингового события;
— регионы, в которых будет проводиться рекламная кампания;
— дата начала кампании;
— дата завершения кампании.

`final_ab_new_users.csv` — пользователи, зарегистрировавшиеся с 7 по 21 декабря 2020 года.

— идентификатор пользователя;
— дата регистрации;
— регион пользователя;
— устройство, с которого происходила регистрация.

`final_ab_events.csv` — действия новых пользователей в период с 7 декабря 2020 по 4 января 2021 года.

— идентификатор пользователя;
— дата и время покупки;
— тип события;
— дополнительные данные о событии. Например, для покупок, `purchase,` в этом поле хранится стоимость покупки в долларах.

`final_ab_participants.csv` — таблица участников тестов.

— идентификатор пользователя;
— название теста;
— группа пользователя.

## Выводы:

- Было проведено 2 теста - recommender_system_test и interface_eu_test. В каждом тесте присутстсвуют экспериментальная и контрольная группы.
- При уровне значимости в 0.01 у нас статистически подтверждены различия в конверсии в просмотр карточек товаров (при этом конверсия в экспериментальной группе меньше, чем в контрольной). Различия в конверсиях в просмотр корзины и покупки статически подтвердить не удалось.
- Выборка была подобрана корректно, но эксперимент можно признать неудачным.
- Основная рекомендация для последующих экмпериментов - менять параметры рекомендательной системы и повторно проводить тесты на корректно отобранных выборках.

**Использованные библиотеки**: pandas, math, numpy, seaborn, matplotlib, scipy, plotly

**Статус исследования:** завершено
