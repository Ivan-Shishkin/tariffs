# Описание проекта

Клиентам предлагают два тарифных плана: «Смарт» и «Ультра». Чтобы скорректировать рекламный бюджет, коммерческий департамент хочет понять, какой тариф приносит больше денег.
Предстоит сделать предварительный анализ тарифов на небольшой выборке клиентов. В распоряжении данные 500 пользователей «Мегалайна»: кто они, откуда, каким тарифом пользуются, сколько звонков и сообщений каждый отправил за 2018 год. Нужно проанализировать поведение клиентов и сделать вывод — какой тариф лучше.

# Описание тарифов

### Тариф смарт

1. Ежемесячная плата: 550 рублей


2. Включено 500 минут разговора, 50 сообщений и 15 Гб интернет-трафика


3. Стоимость услуг сверх тарифного пакета:

    - минута разговора: 3 рубля

    - сообщение: 3 рубля

    - 1 Гб интернет-трафика: 200 рублей
    
 ###  Тариф ультра
 
1. Ежемесячная плата: 1950 рублей


2. Включено 3000 минут разговора, 1000 сообщений и 30 Гб интернет-трафика


3. Стоимость услуг сверх тарифного пакета:

    - минута разговора: 1 рубль
    - сообщение: 1 рубль
    - 1 Гб интернет-трафика: 150 рублей
    
# Описание данных

1. **Таблица `users` (информация о пользователях):**

    - user_id — уникальный идентификатор пользователя
    
    - first_name — имя пользователя
    
    - last_name — фамилия пользователя
    
    - age — возраст пользователя (годы)
    
    - reg_date — дата подключения тарифа (день, месяц, год)
    
    - churn_date — дата прекращения пользования тарифом (если значение пропущено, то тариф ещё действовал на момент выгрузки данных)
    
    - city — город проживания пользователя
    
    - tariff — название тарифного плана
    
    
2. **Таблица `calls` (информация о звонках):**

    - id — уникальный номер звонка
    
    - call_date — дата звонка
    
    - duration — длительность звонка в минутах
    
    - user_id — идентификатор пользователя, сделавшего звонок
    
    
3. **Таблица `messages` (информация о сообщениях):**

    - id — уникальный номер сообщения
    
    - message_date — дата сообщения
    
    - user_id — идентификатор пользователя, отправившего сообщение
    
    
4. **Таблица `internet` (информация об интернет-сессиях):**

    - id — уникальный номер сессии
    
    - mb_used — объём потраченного за сессию интернет-трафика (в мегабайтах)
    
    - session_date — дата интернет-сессии
    
    - user_id — идентификатор пользователя
    
    
5. **Таблица `tariffs` (информация о тарифах):**

    - tariff_name — название тарифа
    
    - rub_monthly_fee — ежемесячная абонентская плата в рублях
    
    - minutes_included — количество минут разговора в месяц, включённых в абонентскую плату
    
    - messages_included — количество сообщений в месяц, включённых в абонентскую плату
    
    - mb_per_month_included — объём интернет-трафика, включённого в абонентскую плату (в мегабайтах)
    
    - rub_per_minute — стоимость минуты разговора сверх тарифного пакета (например, если в тарифе 100 минут разговора в месяц, то со 101 минуты будет взиматься плата)
    
    - rub_per_message — стоимость отправки сообщения сверх тарифного пакета
    
    - rub_per_gb — стоимость дополнительного гигабайта интернет-трафика сверх тарифного пакета (1 гигабайт = 1024 мегабайта)
    
# План проекта

1. **Чтение данных**


2. **Предобработка данных**

    - приводим данные к нужным типам
    
    - находим и исправляем ошибки в данных
    
    - для каждого пользователя считаем
 
        - количество сделанных звонков и израсходованных минут разговора по месяцам;
        - количество отправленных сообщений по месяцам;
        - объем израсходованного интернет-трафика по месяцам;
        - помесячную выручку с каждого пользователя
    
    
3. **Анализ данных**

    - посчитаем сколько минут разговора, сколько сообщений и какой объём интернет-трафика требуется пользователям каждого тарифа в месяц
    - посчитаем среднее количество, дисперсию и стандартное отклонение
    - постройте гистограммы
    - опишем распределения
    
 
4. **Проверяем гипотезы**

    - средняя выручка пользователей тарифов «Ультра» и «Смарт» различается
    - средняя выручка пользователей из Москвы отличается от выручки пользователей из других регионов
    

5. **Общий вывод**
