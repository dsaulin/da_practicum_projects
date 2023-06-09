# Исследование гипотез для увеличения выручки магазина

## Цель исследования:

Приоритезация гипотез и анализ результатов A/B-теста для увеличения выручки магазина;

## Использованные данные:

Файл hypothesis:

    Hypothesis — краткое описание гипотезы;
    Reach — охват пользователей по 10-балльной шкале;
    Impact — влияние на пользователей по 10-балльной шкале;
    Confidence — уверенность в гипотезе по 10-балльной шкале;
    Efforts — затраты ресурсов на проверку гипотезы по 10-балльной шкале. Чем больше значение Efforts, тем дороже проверка гипотезы.

Файл orders:

    transactionId — идентификатор заказа;
    visitorId — идентификатор пользователя, совершившего заказ;
    date — дата, когда был совершён заказ;
    revenue — выручка заказа;
    group — группа A/B-теста, в которую попал заказ.

Файл visitors:

    date — дата;
    group — группа A/B-теста;
    visitors — количество пользователей в указанную дату в указанной группе A/B-теста

## Выводы:

- В зависимости о методики расчета приоритеты гипотез меняются (изменения при этом внутри топ-5). Во втором случае (RICE) на первое место попадает гипотеза о добавлении формы подписки (т.к. она коснется бОльшего количества пользователей), а рекордсмен 1-го расчета (акция на скидку в день рождения) сместилась на 5-е место в этомтопе.
- В А/В тестировании нет статистически значимого различия по среднему чеку между группами ни по «сырым», ни по данным после фильтрации аномалий. При этом после очистки данных соотношение средних чеков изменилось в пользу группы А;
- При этом есть разница в конверсии между группами есть и при расчетах "сырых" данных и после очистки данных от выбросов;
- По сделанным выводам мы бы рекомендовали остановить тест и признать победу группы В: хотя выбросы и влияют на размер чека группы В, но количество заказов у группы В статистически значимо больше, а значит различие между этими группами приводит к разнице экономических показателей. 

**Использованные библиотеки**: pandas, math, numpy, seaborn, matplotlib, scipy

**Статус исследования:** завершено
