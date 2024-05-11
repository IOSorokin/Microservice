# Задача 1: Интернет Магазин
    Руководство крупного интернет магазина у которого постоянно растёт пользовательская база и количество заказов рассматривает возможность переделки своей внутренней ИТ системы на основе микросервисов.
Вас пригласили в качестве консультанта для оценки целесообразности перехода на микросервисную архитектуру.
Опишите какие выгоды может получить компания от перехода на микросервисную архитектуру и какие проблемы необходимо будет решить в первую очередь.
  
## Решение
  Выгоды:
    В распределенной системе снижается зависимость между компонентами.
    Возможно оперативно наращивать мощности, за счет горизонтального масштабирования и обратно сокращать объем системы при снижении нагрузки.
    Снижать риски деградации системы и полного отказа за счет отсутствия единой точки отказа, повышенная работоспособность.
    Возможность использования различных стеков и технологий, в зависимости от архитектуры и потребности конкретного микросервиса, а не всей системы в целом (различные типы БД в разных микросервисах, разные языки программирования и т.п.).
    
    Повышение возможности делать более частые релизы, т.е. быстрее выводить новые функции и фичи и ускорение тестирование - тестирование отдельных сервисов, а не монолитной системы с регресстестированием при модификации какой-либо части.
    За счет повторения сервисами структуры коммуникации организации, можно создать более гармоничную систему при разделении команд на разных сервисах с разными задачами и бизнес целями.
    Повышение отказоустойчивости и скорости восстановления. В случае проблем в одном из модуля (микросервиса), будет недоступен функционал этого модуля, а не система целиком.
    Балансировка нагрузки, возможность репликации наиболее нагруженных компонентов на несколько нод системы (при необходимости между несколькими географически распределенными площадками)

  Проблемы:

    На первом этапе потребуется проработать вопросы целевой архитектуры продукта, выделение микросервисов. Выбрать стек инфраструктуры, создать инфраструктуру. Сформировать команды и определить стек каждого микросервиса.
    Микросервисы не являются решением всех проблем. Решать проблемы вычислительных мощностей и инфраструктуры так же придется.
    Необходимо найти баланс и не дробить систему слишком сильно. Можно чрезмерно усложнить систему большим количеством мелких сервисов.
    Изменение оргструктуры организации, разделение на команды и изменение состава команд.
    Так же необходимо повышать квалификацию инженеров и разработчиков, их функциональных обязанностей (документирование, версионирование). Вероятно придется расширить штат разработчиков в связи с распределением систем и разделением команд для разных сервисов.
    Возможно введение дополнительной службы (возможно внтурикомандного распределение обязанностей) - DevOps
