# Домашнее задание к занятию «Микросервисы: подходы»

Вы работаете в крупной компании, которая строит систему на основе микросервисной архитектуры. Вам как DevOps-специалисту необходимо выдвинуть предложение по организации инфраструктуры для разработки и эксплуатации.

## Задача 1: Обеспечить разработку

    Предложите решение для обеспечения процесса разработки: хранение исходного кода, непрерывная интеграция и непрерывная поставка. Решение может состоять из одного или нескольких программных продуктов и должно описывать способы и принципы их взаимодействия.

Решение должно соответствовать следующим требованиям:

-    облачная система;
-    система контроля версий Git;
-    репозиторий на каждый сервис;
-    запуск сборки по событию из системы контроля версий;
-    запуск сборки по кнопке с указанием параметров;
-    возможность привязать настройки к каждой сборке;
-    возможность создания шаблонов для различных конфигураций сборок;
-    возможность безопасного хранения секретных данных (пароли, ключи доступа);
-    несколько конфигураций для сборки из одного репозитория;
-    кастомные шаги при сборке;
-    собственные докер-образы для сборки проектов;
-    возможность развернуть агентов сборки на собственных серверах;
-    возможность параллельного запуска нескольких сборок;
-    возможность параллельного запуска тестов.

Обоснуйте свой выбор.

### Ответ:
     Если решение не было интегрировано, и это начало запуска CI/CD в производственный процесс с чистого листа, стоит остановить свое внимание на Gitlab. Он уже содержит в себе весь необходимый функционал который централизован и удобно администрируется. Так же он имеет обширное комъюнити. Останется решить проблему с хранением различных секретов, так как в Gitlab нет встроенного решения, а хранить секреты в переменных не самый лучший вариант. Для решение данной задачи можно обратить внимание на еще один известный и часто используемый инструмент Hashicorp vault.


## Задача 2: Логи

  Предложите решение для обеспечения сбора и анализа логов сервисов в микросервисной архитектуре. Решение может состоять из одного или нескольких программных продуктов и должно описывать способы и принципы их взаимодействия.

  Решение должно соответствовать следующим требованиям:

-    сбор логов в центральное хранилище со всех хостов, обслуживающих систему;
-    минимальные требования к приложениям, сбор логов из stdout;
-    гарантированная доставка логов до центрального хранилища;
-    обеспечение поиска и фильтрации по записям логов;
-    обеспечение пользовательского интерфейса с возможностью предоставления доступа разработчикам для поиска по записям логов;
-    возможность дать ссылку на сохранённый поиск по записям логов.

Обоснуйте свой выбор.

### Ответ

 - Самым популярным и известным решением является стек ELK он набрал большую популярность и в основном с ним все работали.
 - Менее ресурсоёмкий и более эффективный стек в плане сжатия, но проседающий по функционалу будет стек в котором хранилищем является: Clichouse Иструменты для передачи логов и используемые графические оболочки меняются, поэтому я укажу одни из вариантов: Vector для сбора и передачи логов в хранилище Lighthouse веб-интерфейс для Clichouse

  Выбор будет зависеть от наличия специалистов которые работали с тем или иным стеком, а так же от количества доступных ресурсов.

## Задача 3: Мониторинг

  Предложите решение для обеспечения сбора и анализа состояния хостов и сервисов в микросервисной архитектуре. Решение может состоять из одного или нескольких программных продуктов и должно описывать способы и принципы их взаимодействия.

  Решение должно соответствовать следующим требованиям:

  -  сбор метрик со всех хостов, обслуживающих систему;
  -  сбор метрик состояния ресурсов хостов: CPU, RAM, HDD, Network;
  -  сбор метрик потребляемых ресурсов для каждого сервиса: CPU, RAM, HDD, Network;
  -  сбор метрик, специфичных для каждого сервиса;
  -  пользовательский интерфейс с возможностью делать запросы и агрегировать информацию;
  -  пользовательский интерфейс с возможностью настраивать различные панели для отслеживания состояния системы.

Обоснуйте свой выбор.

### Ответ

  Для решения данной задачи есть популярное решение в виде стека:
  node_exporter Передача метрик с узлов Prometheus сбор метрик Grafana визуализация метрик
  Преимуществ у данного решения несколько:
  1. производительно, данный стек потребляет крайне малое количество ресурсов
  2. Средство визуализация Grafana обладает мощным визуализационным функционалом.
  3. Данный стек популярен и имеет большое комьюнити и легко настраивается.
