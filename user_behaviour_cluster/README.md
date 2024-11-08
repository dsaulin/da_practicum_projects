# Выделение групп пользователей мобильного приложения на основе поведения

## Цель исследования:

Выделить группы пользователей приложения "Ненужные вещи", которые различаются по четырем метрикам (retention rate, время, проведённое в приложении, частота действий, конверсия в целевое действие "просмотр контактов".)

## Использованные данные:

Датасет mobile_dataset.csv содержит колонки:

— время совершения
— название события
 — идентификатор пользователя
 
Датасет mobile_sources.csv содержит колонки:

— идентификатор пользователя
— источник, с которого пользователь установил приложение

Расшифровки событий:

`advert_open` — открытие карточки объявления
`photos_show` — просмотр фотографий в объявлении
`tips_show` — пользователь увидел рекомендованные объявления
`tips_click` — пользователь кликнул по рекомендованному объявлению
`contacts_show` и `show_contacts` — пользователь нажал на кнопку "посмотреть номер телефона" на карточке объявления
`contacts_call` — пользователь позвонил по номеру телефона на карточке объявления
`map` — пользователь открыл карту размещенных объявлений
`search_1` — `search_7` — разные события, связанные с поиском по сайту
`favorites_add` — добавление объявления в избранное

## Выводы:

- Пользователи мобильного приложения "Ненужные вещи" были разбиты на 3 группы. Третий кластер с сильным отрывом демонстрирует удержание. Первый кластер, несмотря на меньшую активность, по удержанию чуть лучше, чем второй.
- Графики демонстрируют максимальную конверсию у третьего кластера, она в 1,5 раза больше, чем конверсия 2-го кластера, и довольно сильно растет в течение лайфтайма.
- Первую нулевую гипотезу мы отвергнуть не можем. Что означает, что нет статистически важного различия в конверсии в целевое действие между пользователями Яндекса и Гугла (при этом, судя по количеству юзеров - каждое действие юзеры, пришедшие по ссылкам Яндекса, совершают чаще.)
- Вторую нулевую гипотезу мы отвергнуть не можем. Т.е. статистически важное различие в конверсии в целевое действие между юзерами 1 и 3 неделями месяца и пользователями 2 и 4 неделей мы не обнаруживаем.
- В среднем пользователь проводит в приложении 83 минуты, медианное же значение - 11,8 мин.

## Рекомендации по развитию приложения:
- Яндекс-пользователи - многочисленная группа, при этом их конверсия, будучи близкой к средней (ок 22%) всё же меньше, чем у ядра пользователей. Можно сосредоточиться на увеличении конверсии этого довольно многочисленного кластера;
- Третий кластер - самый небольшой, но самый активный и с большой конверсией. Если понять, что важно именно для этих пользователей в приложении, возможно увеличить эту группу за счет перетекания юзеров из других кластеров (хотя, конечно обычно ядро резко вырасти не может.)
- Интересно понять, почему самый крупный кластер (первый) проводит мало времени в приложении и можно ли увеличить это время, а также увеличить конверсию. Возможно, дело в типах товаров и услуг этого кластера (например, аренда квартир, когда решения принимаются быстро.) Но проблема может крыться в том, что за 1-й день юзеры не находят удачных вариантов и потому уходят, демонстрируя низкую конверсию. 
- О том, что система рекомендаций не идеальна говорит также то, что реже всего юзеры они кликают по рекомендованному объявлению и добавляют товар в любимые. Скорее всего нужна корректировка рекомендацией в зависимости от кластера. 

**Использованные библиотеки**: pandas, math, numpy, seaborn, matplotlib, scipy, plotly, sklearn

**Статус исследования:** завершено
