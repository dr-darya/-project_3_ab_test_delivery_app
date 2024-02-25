# Оценка результатов АБ теста - Кейс приложение доставки
> Стек - python pandas numpy matplotlib scipy seaborn plotly math A/B тестирование

### Описание задачи 
В приложение внедрили умную систему рекомендации товаров – предполагается, что такая система поможет пользователям эффективнее работать с приложением и лучше находить необходимые товары.
Был проведен АБ - тест для проверки эффективности системы рекомендаций. 
В группе 1 - пользователи с новой системой рекомендации, в группе 0 - пользователи со старой версией приложения, где нет рекомендации товаров.

**Цель**

Оценить, смогла ли новая система рекомендаций принести пользу бизнесу и пользователям приложения. 

________
### Этапы реализации
1. Выделила пять метрик для анализа, которые отвечают за качество сервиса:
   -  Количество отмененных заказов
   -  Средний чек
   -  Количество активных пользователей(DAU)
   -  Среднее кол-во товаров в заказах
   -  Кол-во созданных заказов

2. Статистически их сравнила в двух группах. 

### Результат
Статистический анализ метрик показал, что в группе пользователей с новой системой рекомендаций - статистически увеличилось количество активных юзеров, они стали больше создавать заказов, больше добавлять товаров в корзину, но вместе с этими показателями и статистически значимо увеличилось количество отмененных заказов в этой группе. Что логично.
Также я анализировала метрику средний чек в группах. Анализ не дал статистически значимых различий. По моей логике, при росте числа заказов, средний чек пользователя должен вырасти, но получается, что средний чек не вырос. Поэтому, думаю, что не стоит выкатывать новый алгоритм.

___
### Данные 
- ab_users_data – история заказов пользователей, в этой таблице есть информация о том, какие заказы создавали и отменяли пользователи
- ab_orders – подробная информация о составе заказа, тут для каждого заказа есть список id тех продуктов, которые были включены в заказ
- ab_products – подробная информация о продуктах, их название и стоимость
