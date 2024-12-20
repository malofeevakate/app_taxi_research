## Задача: ##  
Есть данные о такси-компании (uber), которая хочет изучить отток водителей и посмотреть, какие есть различия между водителями, которые покидают сервис, и которые остаются. 
Нужно сформулировать и протестировать гипотезы, выделить группы водителей, которые наиболее подвержены "оттоку". На основе результатов сделать выводы о том, что можно улучшить в сервисе, чтобы в дальнейшем внести изменения.

## Стек: ##  
pandas, numpy, seaborn, matplotlib, scipy (chi2_contingency, shapiro, kruskal, mannwhitneyu)  

## Реализация: ##  
1. Проведен EDA,
2. Проверена гипотеза о влиянии платформы на поведение юзеров с помощью критерия независимости хи-квадрат,  
3. Проверена гипотеза о влиянии городов проживания на поведение юзеров с помощью критерия независимости хи-квадрат,  
4. Проверены на нормальность распределения поездок в разных городах в первый месяц,  
5. Проведено сравнение распределений поездок в первый месяц в городах с помощью критерия Краскела - Уоллиса,  
6. Сравнены активности оставшихся и ушедших юзеров в первые 30 дней с помощью критерия Манна - Уитни

## Результат: ##  
Статистически значимые различия в поведении юзеров наблюдаются в разрезе платформ, городов и первоначальной активности, поэтому:  
1. Необходимо рассмотреть особенности работы приложения на платформе андроид, возможны баги
2. Нужен дополнительный анализ работы приложения и рынков такси в двух городах из трех (возможно, зашел более выгодный для юзеров конкурент?)
3. Поскольку ушедшие юзеры были изначально менее активны, возможно стоит рассмотреть вариант улучшения программы лояльности и бонусов для водителей, или улучшить таргетинг

## Описание данных: ##  
- city – город  
- phone – основное устройство, которое использует водитель  
- signup_date – дата регистрации аккаунта (YYYYMMDD)  
- last_trip_date – дата последней поездки (YYYYMMDD)  
- avg_dist – среднее расстояние (в милях) за поездку в первые 30 дней после регистрации  
- avg_rating_by_driver – средняя оценка поездок водителем  
- avg_rating_of_driver – средняя оценка поездок водителя  
- surge_pct – процент поездок, совершенных с множителем > 1 (кажется когда большая загруженность и тд)  
- avg_surge – средний множитель всплеска за все поездки этого водителя  
- trips_in_first_30_days – количество поездок, которые совершил водитель в первые 30 дней после регистрации  
- luxury_car_user – TRUE, если пользователь в первые 30 дней использовал премиум-автомобиль  
- weekday_pct – процент поездок пользователя, совершенных в будние дни  
