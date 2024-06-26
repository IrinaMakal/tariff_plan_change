# Направления смен тарифных планов
<br>Необходимо исследовать следующие вопросы:
<br>1. Направления смен тарифных планов: с каких тарифных планов и на какие шли  наибольшие перетоки? Визуализировать потоки миграций на диаграмме. 
<br>2. Насколько изменился среднемесячный счет абонентов за период 3 месяца после месяца смены тарифного плана в сравнении с периодом 3 месяца до месяца смены тарифного плана. Какие направления смен тарифных планов характеризовались ростом среднего счета в трехмесячном периоде, а какие – сокращением.  Визуализировать результаты на диаграммах.
<br>3. Аналогично п.2, только относительно изменения уровня блокировок: насколько реже или чаще стали попадать в блокировки абоненты после миграции в целом и для каждого направления миграции в отдельности. Для сравнения использовать те же периоды: 3 месяца до месяца смены плана и 3 месяца после месяца смены.
<br>
<br>**Стек:** Pandas, Requests, Numpy, Seaborn
<br>
<br>В файле **Tariff_plans_change.csv** содержатся выборочные данные о транзакциях, связанных с подключениями и отключениями тарифных планов абонентами, которые меняли тарифные планы в первом полугодии 2017 года: 
<br>SUBSCRIBER_ID	 -  условный идентификатор абонента
<br>TARIFF_PLAN_ID – условный идентификатор тарифного плана	
<br>START_DTTM	 - дата и время подключения плана
<br>END_DTTM – дата и время отключения (значение $null$ означает, что план актуален на текущий момент).
<br>
<br>В файле **Charges.csv** содержатся помесячные исторические данные об общих расходах абонентов на мобильную связь:
<br>SUBSCRIBER_ID	 -  условный идентификатор абонента
<br>BILL_MONTH – биллинговый период в формате YYYY-MM-01 (например, строки со значением ‘2016-01-01’ содержат данные о расходах и потреблении за январь 2016 года)
<br>CHARGES – общая сумма  счета за услуги связи
<br>
<br>В файле **Suspended.csv** содержатся исторические данные о блокировках абонентов в транзакционной форме:
<br>SUBSCRIBER_ID	 -  условный идентификатор абонента
<br>START_DT - дата начала блокировки
<br>END_DT – дата окончания блокировки (значение $null$ означает, что абонент остается блокированным на текущий момент).
<br>
<br>Для решения поставленных задач проводим предобработку данных, объединяем таблицы, аггрегируем данные (согласно требованиям), после чего визуализируем полученные результаты с помощью Seaborn и делаем выводы.
<br>
<br>*Выводы по проекту:*
<br>**1.** Большие перетоки пользователей за анализируемый период наблюдались с 1 на 5 т.п. и с 3 на 5 т.п.
<br>**2.** Среднемесячный счет абонентов за период 3 месяца после месяца смены тарифного плана значительно снизился в сравнении с периодом 3 месяца до месяца смены тарифного плана..
<br>**3.** Среднемесячный счет абонентов в разрезе потоков смены тарифных планов за период 3 месяца после месяца смены тарифного плана преимущественно снижался в сравнении с периодом 3 месяца до месяца смены тарифного плана. Рост наблюдался только для потоков 3->2, 4->3, 4->4 и 5->3.
<br>И это при том, что большие перетоки количества пользователей наблюдались по 1->5 и 3->5, по которым мы наблюдаем падение среднего счета.
<br>**4.** Количество заблокированных абонентов за период 3 месяца после месяца смены тарифного плана значительно снизился в сравнении с периодом 3 месяца до месяца смены тарифного плана.
<br>**5.** Среднее количество заблокированных абонентов за период 3 месяца после месяца смены тарифного плана преимущественно снижалось в сравнении с периодом 3 месяца до месяца смены тарифного плана.
<br>Рост наблюдался только для потоков 2->4, 5->4 и 5->3.
<br>
