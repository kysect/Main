# Projects

Мы занимаемся разработкой разных проектов и всегда рады помощи с ними. Если у вас есть желание в каком-то из них принять участие, то в первую очередь стоит написать и узнать о проекте. В дискорде есть специальные каналы с обсуждением определённых проектов, куда вас добавят, если вам что-то будет интересно. Вопросы лучше задавать там.

## Shreks

- Линк: https://github.com/kysect/Shreks
- Статус: В активной разработке
- Описание: Система предназначена для автоматизации процесса обучения, а именно: процессов отправки заданий студентами, формирования очереди и оценивания заданий преподавателями.
- Чем можно заняться в рамках проекта:
  - Реализация интеграции с Github API, работа с вебхуками, разработка Github App;
  - Реализация интеграции с Google Sheet, написание логики создания и форматирования таблиц, их динамическое изменение;
  - Разработка Web UI с использованием Blazor для администрирования системой;
  - Расширение логики работы сложного домена, проектирование пользовательских сценариев.

## Recademy

- Линк: https://github.com/kysect/Recademy
- Статус: В активной разработке
- Описание: Сервис для поддержания жизни Kysect с элементами геймификации. Личные профили, ачивки и другие способы геймификации.
- Чем можно заняться в рамках проекта:
  - Проработка и реализация идей по геймификации жизни людей в Kysect;
  - Реализация Web UI для сервиса с использованием Blazor;
  - Интеграция с различными системами (Github, Wakatime, Discord) для агрегации данных об активности;
  - Разработка Discord бота для работы с системой прямо из сервера.

## AssignmentReporter

- Линк: https://github.com/kysect/AssignmentReporter
- Статус: Реализован минимальный необходимый функционал, который можно доработать
- Описание: Инструмент для генерации шаблонных отчётов о выполнении университетских работ. Основная идея проекта - научиться генерировать шаблонный отчет на основании репозитория с кодом. В большинстве случаев именно такой отчёт и требуют.
- Чем можно заняться в рамках проекта:
  - Работа с git для управления репозиториями - клонирование, смена веток;
  - Доработка функционала по генерации отчёта - интеграция с Github, поддержка .gitignore для фильтров и прочее.

## DetCheckR

- Линк: Приватный репозиторий
- Статус: Есть рабочее приложение, которое нужно дорабатывать - реализация веб-сервиса, улучшение UX, интеграция с Github
- Описание: Система поиска схожести кода в файлах между репозиториями. Используется для выявления плагиата в работах студентов
- Чем можно заняться в рамках проекта:
  - Интеграция с Github для анализа Pull request, различных веток и в целом репозиториев организации;
  - Поддержка moss в качестве внешнего анализатора;
  - Разработка более сложных алгоритмов сравнения исходного кода на основе Roslyn - компилятор исходного кода C#;
  - Разработка системы для управления результатами сравнения и предоставление её as a service;
  - Разработка Desktop UI для управления конфигурацией и параметрами проверки;
  - Разработка алгоритмов анализа исходного кода на наличие аномалий.

## GithubUtils

- Линк: https://github.com/kysect/GithubUtils
- Статус: Реализованы отдельные функции, которые можно дорабатывать и улучшать UX
- Описание: Библиотека, где собран код для работы с git и Github, который используется в других проектах - парсер активности, алгоритм рассылки приглашений в организацию, алгоритм многопоточного клонирования и синхронизации всех репозиториев в организации
- Чем можно заняться в рамках проекта:
  - Реализация и доработка парсеров Github активности;
  - Оптимизация и доработка алгоритмов клонирования и синхронизации репозиториев организации.

## BotFramework

- Линк: https://github.com/kysect/BotFramework
- Статус: реализован базовый функционал
- Описание: Мини фреймворк для создание чат-ботов для различных платформ
- Чем можно заняться в рамках проекта:
  - Расширение функционала парсинга команд, более полная поддержка провайдеров API;
  - Применение фреймворка для реализации ботов.

## Tamgly

- Линк: https://github.com/kysect/Tamgly
- Статус: Реализован Proof of concept, требуется реализовать DAL, UI и доработать функционал
- Описание: Yet another time tracker для управления задачами, планированием и элементами поддержки принятия решения за счёт анализа нагруженности
- Чем можно заняться в рамках проекта:
  - Реализация Data access layer, проектирование базы данных, таблиц;
  - Реализация Desktop UI для управления задачами;
  - Интеграция с MS Todo, Clockify и т.д.;
  - Реализация алгоритмов определения нагруженности пользователя задачами и автоматический подсчёт эстимейтов.

## Quewer

- Линк: https://github.com/kysect/Quewer
- Статус: Реализован минимальный набор классов и общий каркас приложения
- Описание: Библиотека для управления очередью, которую можно использовать для сдач в рамках учебного процесса.
- Чем можно заняться:
  - Интеграция в бот фреймворком;
  - Реализация основного функционала очередей.

## Fluda

- Линк: https://github.com/kysect/Fluda
- Статус: Проект реализован в том виде, в котором планировался, но есть идеи для доработки
- Описание: Самописная ORM для работы с базой данных, которая позволяет делать запросы как к локальной базе данных, так и удалённой за счёт безопасной сериализации запросов. В целом решение получилось довольно специфичное и будет интересно только тем, кто хочет познать дзен работы с базой данных
- Чем можно заняться:
  - Если очень скучно - научить ORM работать в Excel в качестве базы для хранения;
  - Поддержка batch запросов, Union, Like;
  - Доработка и улучшение генератора кода написанного на Roslyn.

## GitDirectorySyncer

- Линк: https://github.com/kysect/GitDirectorySyncer
- Статус: Описано ТЗ, создан пустой проект
- Описание: Тула, которая позволяет синхронизировать две разные директории. Основной кейс, который она решает - предоставляет возможность синхронизировать гит репозиторий с папкой, которая находится на облачном диске не копируя при этом не нужные файлы (папку .git/).
- Чем можно заняться:
  - Разработка логики копирования директорий, алгоритмов синхронизации файлов;
  - Разработка Data access layer для хранения информации о работе системы;
  - Разработка интеграции с OneDrive, Google Drive, etc.
