# Senior Crossfunc QA — список требований

Отмечай `[x]`, когда тема пройдена (теория + практика).

---

## 1. Code Quality Control (CQC)

**Правила сдачи**
- 6–8 информативных PR за последние 3 месяца (если меньше — решает эксперт)
- Язык кода в PR = язык экзамена (инструмент может отличаться)
- Экспорт в `.mhtml` или `.diff`, ZIP-архив, отправка эксперту через Outlook
- Результат действует 4 месяца; пересдача не раньше чем через 2 месяца
- При недостатке кода эксперт может дать дополнительное задание

**Неинформативные PR:** переименование, форматирование, изменения конфигов/properties, тесты только из готовых шагов

**Критерии оценки** (оценивается только новый код автора)
- [ ] Соответствие guidelines: PEP 8, PEP 257, BDD guidelines, стабилизация и оптимизация тестов
- [ ] Читаемость: понятная логика, хорошие имена переменных, функций, классов
- [ ] Производительность: эффективность алгоритмов, ресурсы, узкие места
- [ ] Архитектурная согласованность: модульность, структура компонентов
- [ ] Отсутствие дублирования: переиспользуемые функции и классы
- [ ] Обоснованность решений: нестандартные подходы и отступления от guidelines объяснены
- [ ] Низкая когнитивная сложность: без глубокой вложенности и лишних условий

---

## 2. Python & Software design patterns and principles

### Python — KP1
- [ ] Building a project: добавить библиотеку через pip и requirements.txt; установить и настроить интерпретатор
- [ ] Lambda: как использовать
- [ ] Type casting: implicit и explicit
- [ ] Data types: поддерживаемые типы данных
- [ ] Operators: арифметические, increment/decrement, логические
- [ ] OOP: принципы и конструкции языка для их реализации
- [ ] Control statements: if / else / elif, тернарный оператор
- [ ] Loops: for, while
- [ ] Classes: что такое класс, `self`, `__dict__`, объявление, наследование, класс vs экземпляр
- [ ] Methods: обычные, static, class methods; вызов методов родителя; `*args` и `**kwargs`
- [ ] Exceptions: что это, как перехватить, как выбросить
- [ ] Comments: что это, как писать, когда нужны
- [ ] Conventions и style-checkers: что это, как использовать, PEP 8, Flake8
- [ ] String formatting: методы работы со строками, способы форматирования
- [ ] Data structures: из чего состоят, зачем нужны, разница List / Dict / Set / FrozenSet / Tuple / String / Bytearray
- [ ] Working with files: чтение и запись текстовых файлов; сериализация и десериализация XML / JSON

### Python — KP2
- [ ] Python versions: переключение между версиями интерпретатора
- [ ] Classes: абстрактный класс, множественное наследование, property, интерфейс, декоратор
- [ ] Data types: mutable vs immutable, в чём разница
- [ ] List comprehension: фильтрация, сортировка, группировка; проверка наличия элемента и дубликатов; объединение структур
- [ ] Logging: зачем, какие библиотеки, чем отличаются

### Python — KP3
- [ ] Interpreter: как работает, отличие от компилятора, использует ли Python C/C++
- [ ] Multithreading: создать поток, выполнить действия, завершить; остановить поток; синхронизация; передача данных между потоками; GIL

### Design patterns — KP1
- [ ] Page Object: как реализовать (правила, требования), когда обязателен
- [ ] Framework & project structure: классическая структура (например, Aquality); работа с конфигами, тестовыми данными, константами; работа с секретами и чувствительными данными; как добавить новую фичу во фреймворк

### Design patterns — KP2
- [ ] Builder: реализация, когда нужен
- [ ] Delegation вместо Inheritance: как и зачем
- [ ] Singleton и альтернативы (Object Pool, thread-safe Singleton): когда и как
- [ ] Chain of Responsibility: что это, когда нужен, реализация
- [ ] Lazy initialization: реализация, когда полезна
- [ ] Factory Method: реализация, когда полезен

### Design patterns — KP3
- [ ] SOLID: SRP, OCP, LSP, ISP, DIP — объяснить на примерах
- [ ] Observer
- [ ] Abstract Factory
- [ ] Proxy
- [ ] Dependency Injection
- [ ] Decorator (как альтернатива созданию новых классов)
- [ ] Adapter
- [ ] Prototype
- [ ] Facade
- [ ] Mediator
- [ ] Strategy

Для каждого паттерна: как реализовать и когда он полезен.

---

## 3. Playwright & Pytest & Behave

### Playwright — KP1
- [ ] Navigation: переход по URL, refresh, вперёд/назад
- [ ] Tabs/Windows: iframe (вход и выход), alert (переключиться, обработать), другая вкладка
- [ ] Capabilities: настройки браузера, headless-режим
- [ ] Driver instance: создать экземпляр браузера, корректно закрыть
- [ ] DevTools: basic authorization
- [ ] Elements location: аналоги findElement / findElements, XPath, CSS
- [ ] Elements interaction: клики (обычный, double, JS, context), атрибуты, ввод и получение текста
- [ ] Waits: auto-waiting — когда начинается ожидание и сколько длится
- [ ] Cookies: добавить, удалить, изменить
- [ ] Elements location: relative locators (above / below / left of / right of / near); цепочки локаторов; оптимальный по скорости локатор
- [ ] Elements interaction: загрузка файла

### Playwright — KP2
- [ ] Navigation: ошибки навигации (retry, wait_for_url, таймауты); динамические URL (параметры, query string, hash routing)
- [ ] Tabs & Windows: несколько browser contexts; pop-up окна; context vs page; вложенные iframe
- [ ] Browser settings: профили и окружение (плагины, геолокация, язык); permissions (камера, буфер обмена, уведомления, геолокация); tracing, видео, скриншоты при падении; user agent, viewport, эмуляция устройств
- [ ] Browser instance: пулы и переиспользование контекстов; корректная очистка (try/finally, hooks); параллельный запуск
- [ ] Elements location: locator API с фильтрами (filter, first, nth); динамические локаторы через переменные
- [ ] Elements interaction: динамически появляющиеся элементы (lazy load, infinite scroll); drag-and-drop, hover, scrollIntoView, select; JS evaluation; Shadow DOM

### Playwright — KP3
- [ ] DevTools API: network throttling, логирование, мониторинг консоли, coverage
- [ ] HAR-файлы: запись и анализ
- [ ] Время загрузки страницы и производительность
- [ ] Mock / modify / block запросов
- [ ] Анализ трафика: запросы, статус-коды, payload
- [ ] Валидация заголовков, cookies, тела запросов

### Pytest — KP1
- [ ] Data Driven Testing: когда использовать; синтаксис `parametrize`
- [ ] Pre/postconditions: что в них класть, когда и зачем нужны, разные контексты (scope)
- [ ] Fixtures и conftest: как использовать conftest; передача параметров в фикстуру; factory fixture
- [ ] Основы: простой тест (как пометить, assertions); как пропустить тест

### Pytest — KP2
- [ ] Generated files: стандартный pytest-html отчёт
- [ ] Hooks / расширение фреймворка: получить результат теста; добавить или изменить статусы; интеграция с TestRail; интеграция с Jira
- [ ] Как работают тест-раннеры: последовательность действий при запуске, алгоритм работы
- [ ] Parallel execution: запуск в несколько потоков
- [ ] Grouping: способы группировки тестов

### Behave — KP1
- [ ] BDD tools: подключить библиотеки для behave, настроить, использовать
- [ ] Gherkin: ключевые слова Given / When / Then / And — разница и когда что использовать
- [ ] Step definitions: создание; ограничение параметра определённым типом

### Behave — KP2
- [ ] BDD / KDT: назначение; TDD vs BDD vs ATDD
- [ ] Hooks и tags: как написать hook, когда нужен; теги и отбор тестов по ним
- [ ] Context и stores: передача данных между шагами; виды контекстов
- [ ] Gherkin: Scenario Outline, таблицы, Background
- [ ] Tests execution: связь feature-файлов и step-классов; разные раннеры для запуска

### Behave — KP3
- [ ] BDD best practices: guidelines, check style tools, Cucumber best practices
- [ ] Step argument transformations: как работают, когда использовать, как реализовать (matchers, типы параметров)

### Behave — KP4
- [ ] Test data в BDD: внешние файлы; тестирование локализации; большие объёмы тестовых данных

---

## 4. OpenCV & Selenium & Code-review exam & Technologies of application development

### OpenCV — KP1
- [ ] Установка и подключение к проекту
- [ ] Visual testing: сравнение двух изображений разного качества, размера, цвета; обработка результата

### OpenCV — KP2
- [ ] Распознавание текста на экране; влияние шрифта; распознавание нестандартных шрифтов
- [ ] Распознавание конкретного UI-элемента (кнопка, поле и т.д.)

### Selenium (в исходнике KP1–KP3 не разделены явно)
- [ ] Navigation: переход по URL, refresh, вперёд/назад
- [ ] Tabs/Windows: iframe (вход и выход), alert, другая вкладка
- [ ] Capabilities: директория загрузки по умолчанию; headless; incognito
- [ ] Driver instance: инициализация, корректное закрытие (close vs quit), размер окна (resize, maximize)
- [ ] DevTools: basic authorization; DevTools API (например, данные Network-вкладки во время теста)
- [ ] Elements location: find_element, find_elements, XPath, CSS; стабильный локатор и распознавание нестабильного
- [ ] Relative locators (above / below / left of / right of / near); цепочки; оптимальный по скорости локатор
- [ ] Elements interaction: JS click (когда нужен), атрибуты, send keys, get text, загрузка файла
- [ ] Waits: implicit (когда нужны), explicit (когда нужны), fluent (настройка); почему нельзя смешивать и каким будет итоговое время ожидания
- [ ] Cookies: добавить, удалить, изменить

### Code-review exam
- [ ] Ревью нескольких фрагментов кода на экзамене
- [ ] Не пропустить ни одной Critical или Major проблемы
- [ ] Каждый комментарий объясняет проблему
- [ ] Уметь назвать и объяснить конкретное требование guideline

### Technologies of application development — KP1
- [ ] MVC: что такое Model, View, Controller; как взаимодействуют и разделяются; реализация
- [ ] Monolith vs microservices: разница, реализация
- [ ] Client-Server: архитектура, взаимодействие, плюсы и минусы, реализация

### Technologies of application development — KP2
- [ ] Web-фреймворк для Python (Django): простое приложение
- [ ] CSS: основы стилей, таблица стилей, псевдоклассы
- [ ] CSS-препроцессоры: SASS, LESS, Stylus, PostCSS

---

## 5. Allure & Jenkins & Git

### Allure — KP1
- [ ] Генерация отчёта: serve, generate, open; формат пути к результатам; `--clean`; что нужно для генерации
- [ ] Основные возможности: steps, test cases, test suites
- [ ] Анализ результатов: статусы (что означает каждый, чем отличаются); где найти steps, скриншоты, вложения

### Allure — KP2
- [ ] Интеграция в CI/CD; автоматические сборки (Jenkins)
- [ ] Кастомизация: attachments, bugs, environment; система плагинов; Report Portal; cucumber-html-reporter
- [ ] Настройка по guidelines компании

### Jenkins — KP1
- [ ] Настройка CI-сервера и агентов: общие настройки (JDK, Maven, email и т.д.), плагины, build agents, VCS, команды запуска тестов и сборки
- [ ] Parameterized build: параметры, переменные окружения
- [ ] Build triggers: cron, триггер от другой сборки, ручной
- [ ] Ограничение числа хранимых сборок: когда и как (Discard Old Builds)
- [ ] Шаги до и после сборки (плагины, скрипты, Post-Build Actions)

### Jenkins — KP2
- [ ] Pipelines: назначение, синтаксис, когда использовать, логические конструкции, multi-stage
- [ ] Передача артефактов между сборками
- [ ] Сохранение и публикация артефактов; доступ к результатам через HTML Reporter; отправка результатов в TestRail
- [ ] Build triggers: git hooks, REST API

### Jenkins — KP3
- [ ] CI/CD: что это, как используется в QA
- [ ] Email-уведомления: настройка, кастомные (jelly scripts и т.д.)
- [ ] Администрирование: права доступа (выдать и ограничить)
- [ ] Credentials store: как использовать

### Git — KP1 (можно через GUI)
- [ ] Зачем нужна VCS; что такое Git
- [ ] Commit: из чего состоит, создать, изменить (amend), отменить (restore, reset)
- [ ] Branch: что это, создать, переключиться
- [ ] Merge / rebase: зачем, разница
- [ ] .gitignore: зачем, синтаксис
- [ ] Клонирование репозитория; remote
- [ ] Credentials; уровни конфигурации system / global / local

### Git — KP2 (показывать через CLI)
- [ ] Tags: что это, создать, использовать, переключиться
- [ ] Reset: soft / mixed / hard
- [ ] Squash: что это, зачем, как сделать
- [ ] Stash
- [ ] History: просмотр истории, поиск изменений
- [ ] Из чего состоит VCS; указатель HEAD

### Git — KP3
- [ ] Hooks: настройка; client-side vs server-side
- [ ] Alias: когда полезны, как настроить

---

## 6. Docker & Automation Risks & CI (Azure DevOps / GitLab CI / GitHub Actions) & Regex

### Docker — KP1
- [ ] Запустить существующий контейнер
- [ ] Собрать образ из существующего Dockerfile

### Docker — KP2
- [ ] Создать свой Docker-образ
- [ ] Изменить существующий Dockerfile

### Docker — KP3
- [ ] Docker Compose: использование и управление
- [ ] Docker Swarm: что это, как использовать
- [ ] Kubernetes: что это, как использовать
- [ ] Docker Hub

### Automation risks
Понимать, как влияет на автоматизацию и её результаты, и к чему приводит:
- [ ] Изменения UI
- [ ] Изменения бизнес-логики
- [ ] Большое количество дефектов
- [ ] Проблемы окружения (нестабильные стенды)
- [ ] Проблемы с тестовыми данными
- [ ] Инфраструктурные проблемы (нестабильное соединение)

### CI (Azure DevOps / GitLab CI / GitHub Actions) — KP1
- [ ] Pipelines: назначение, синтаксис, когда использовать, логические конструкции, multi-stage
- [ ] Управление шагами сборки через YAML (conditions, steps, jobs)

### CI — KP2
- [ ] Управление ресурсами и нодами через YAML
- [ ] Ограничение доступа к сборке (permissions)
- [ ] Оптимизация YAML по ресурсам и времени (шаблоны, кэш, best practices)

### Regular Expressions — KP1
- [ ] Извлечь нужную часть текста; проверить, начинается ли слово с…, содержит ли цифры / буквы / спецсимволы

### Regular Expressions — KP2
- [ ] Поиск по частичному совпадению; группы

---

## 7. Katalon & Aquality Tracking

### Katalon — KP1
- [ ] Кастомизация keywords
- [ ] Custom desired capabilities
- [ ] Кастомизация отчётов: логи, отчёты test suite и test suite collection, BDD-отчёты
- [ ] Custom fields и tags

### Aquality Tracking — KP1
- [ ] Установка и настройка
- [ ] Интеграция с фреймворком
- [ ] Кастомизация отчёта
- [ ] Использование AI-модуля
