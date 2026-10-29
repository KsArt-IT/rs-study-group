# Роадмап: Backend (Junior → Senior)

> Теги: roadmap, backend, бэкенд, backend developer, REST API, GraphQL, gRPC, WebSockets, SSE, OpenAPI, Swagger, аутентификация, авторизация, JWT, OAuth, сессии, RBAC, кэширование, Redis, очереди, брокеры сообщений, RabbitMQ, Kafka, BullMQ, безопасность, OWASP, CORS, rate limit, тестирование, масштабирование, микросервисы, observability, SLA, SLO, RPS, latency, сервер не держит нагрузку, как стать backend разработчиком
> Основа: roadmap.sh (Backend, Backend Performance Best Practices), itbooster.ru — Ulbi TV (Backend с 0 до PRO) + дополнения. Проверено 2026-10-24.

## Определение

Backend — серверная часть приложения: бизнес-логика, API, работа с данными, аутентификация, интеграции, фоновые задачи. Backend-разработчик отвечает за корректность, безопасность, производительность и масштабируемость того, что пользователь не видит.

## Зачем / когда использовать

- После [Node.js](roadmap.nodejs.md) и [Баз данных](roadmap.databases.md). Язык в этой базе — Node.js / TypeScript; принципы ниже не зависят от языка.
- Альтернативы языка: Go, Python, Java / Kotlin, C#, PHP, Rust. Совет roadmap.sh: выучить один язык и сделать много проектов, прежде чем браться за следующий.
- Многие темы (масштабирование, распределённые БД) — «знать, что это и когда применять»: большинство никогда не понадобится глубоко.

## Основное

### 1. Фундамент

- [ ] **J** [Основы WEB](roadmap.web-basics.md) — клиент-сервер, HTTP, DNS, хостинг.
- [ ] **J** Язык и среда — [Node.js](roadmap.nodejs.md), IDE.
- [ ] **J** Алгоритмы и структуры данных — основа сейчас, углубиться позже ([алгоритмы](../e.algorithms/algorithms.0-topics.md)).
- [ ] **J** [Git и GitHub](roadmap.git.md).
- [ ] **J** [Базы данных](roadmap.databases.md) — SQL, транзакции, ACID, нормальные формы, миграции, ORM, NoSQL.

### 2. API (первый приоритет)

- [ ] **J** HTTP глубже — методы и идемпотентность, коды статусов, заголовки, cookies, HTTP-кэширование (`Cache-Control`, `ETag`).
- [ ] **J** **REST API** — ресурсы, URL, статусы ошибок, пагинация, фильтрация, сортировка.
- [ ] **J** Валидация входных данных — Zod / class-validator (NestJS).
- [ ] **J** Версионирование API (`/v1`, заголовок).
- [ ] **J** Документирование — OpenAPI / Swagger, кодогенерация клиентов.
- [ ] **M** GraphQL (SDL, резолверы, N+1 и DataLoader); gRPC + protobuf — межсервисное взаимодействие; tRPC — типобезопасный API для TS-монорепо *(опц.)*; SOAP — знать, что существует.
- [ ] **M** Real-time — polling (short / long), WebSockets (Socket.IO), Server-Sent Events.

### 3. Аутентификация и авторизация

- [ ] **J** Аутентификация vs авторизация.
- [ ] **J** Способы — Basic auth, cookie-сессии, токены, **JWT** (access + refresh), **OAuth 2.0** / OpenID Connect (вход через Google / GitHub), SAML *(опц.)*.
- [ ] **J** Хранение паролей — хеширование bcrypt / argon2 / scrypt (не MD5 / SHA для паролей).
- [ ] **M** Роли и права — RBAC, ABAC.
- [ ] **M** Passkeys / WebAuthn, 2FA *(опц.)*; готовые решения — Auth.js, Better Auth, Keycloak, Auth0, Clerk.

### 4. Кэширование

- [ ] **J** Уровни — HTTP-кэш, CDN, кэш приложения, кэш БД.
- [ ] **J** Redis — кэш, TTL, сессии; Memcached *(опц.)*.
- [ ] **M** Паттерны — cache-aside, write-through, read-through; инвалидация кэша.

### 5. Тестирование

- [ ] **J** Unit-тесты, интеграционные (API + БД в Docker / Testcontainers), e2e.
- [ ] **M** Нагрузочное тестирование — k6, Artillery; на базовом уровне — прикинуть RPS, который держит сервис.

### 6. Безопасность

- [ ] **J** **OWASP Top 10** — инъекции (SQL injection), XSS, CSRF, broken access control, SSRF.
- [ ] **J** HTTPS, SSL/TLS, CORS, CSP, безопасные заголовки (helmet).
- [ ] **J** Секреты — переменные окружения, менеджеры секретов; никогда в Git.
- [ ] **M** Rate limiting, защита от brute force, DDoS (на уровне инфраструктуры — Cloudflare / AWS Shield).
- [ ] **M** Безопасность зависимостей — `npm audit`, Dependabot, lock-файлы.

### 7. Архитектура и паттерны

- [ ] **J** Принципы — SOLID, KISS, DRY, YAGNI → [Паттерны и архитектура](roadmap.patterns.md).
- [ ] **M** DI, IoC (встроены в NestJS), паттерны GoF.
- [ ] **M** Архитектуры — слоистая (layered: controller → service → repository), Clean Architecture, Onion, Hexagonal, DDD, event-driven.
- [ ] **M** Монолит, модульный монолит, SOA, микросервисы; Twelve-Factor App.

### 8. Асинхронная обработка

- [ ] **M** Брокеры сообщений — RabbitMQ, Kafka; очереди задач — BullMQ (на Redis).
- [ ] **M** CRON-задачи, фоновые воркеры.
- [ ] **M** Идемпотентность обработчиков, повторные попытки (retry), dead letter queue.

### 9. Инфраструктура для backend

- [ ] **J** Linux, Docker, деплой → [DevOps](roadmap.devops.md), [Docker](roadmap.docker.md).
- [ ] **M** Web-сервер / reverse proxy — Nginx, Caddy; Apache *(знать)*.
- [ ] **M** CI/CD — GitHub Actions / GitLab CI.
- [ ] **M** Поиск — Elasticsearch / OpenSearch; Meilisearch *(опц.)*.

### 10. Наблюдаемость (observability)

- [ ] **M** Логи (структурированные), метрики, трейсы; OpenTelemetry.
- [ ] **M** Стек — Prometheus + Grafana, Loki + Promtail / Grafana Alloy, Sentry; ELK *(опц.)*.
- [ ] **S** SLA, SLO, SLI; golden signals (latency, traffic, errors, saturation).

### 11. Масштабирование и отказоустойчивость (Senior)

- [ ] **S** Масштабирование API — вертикальное и горизонтальное, load balancing, stateless-сервисы.
- [ ] **S** Метрики нагрузки — RPS, latency (p50 / p95 / p99), throughput, concurrency.
- [ ] **S** Масштабирование БД — индексы, репликация, шардирование, распределённые СУБД → [Базы данных](roadmap.databases.md).
- [ ] **S** Отказоустойчивость — graceful degradation, circuit breaker, throttling, backpressure, timeouts и retry с backoff.
- [ ] **S** System design — проектирование систем, собеседования по system design.
- [ ] **S** Serverless, контейнерная оркестрация → [AWS](roadmap.aws.md), [DevOps](roadmap.devops.md).

### 12. AI в backend

- [ ] **M** Интеграция LLM — API провайдеров, streaming, structured outputs, function calling, RAG, эмбеддинги, MCP → [AI-разработка](roadmap.ai.md).

### Чек-лист производительности backend

| Область | Что делать |
|---|---|
| Кэш | HTTP / CDN / Redis; правильная стратегия инвалидации |
| БД | пул соединений; индексы; контроль запросов ORM (N+1); пагинация; без `SELECT *`; slow query log; реплики для чтения |
| Сеть | сервер ближе к пользователям; keep-alive; CDN для статики; сжатие ответов; лимиты на размер payload |
| Асинхронность | тяжёлые задачи — в фоновые очереди; брокеры для межсервисного обмена |
| Код | профилирование; streaming больших ответов; batch-запросы; таймауты и retry; критичные участки — на Go / Rust при необходимости |
| Мониторинг | метрики, логи (асинхронные), регулярные нагрузочные тесты для поиска регрессий |

### Чекпоинт

- [ ] Законченный сервис: REST API (NestJS) + PostgreSQL + Redis + JWT / OAuth + роли + фоновые задачи (BullMQ) + OpenAPI + тесты + Docker Compose + CI.

## Подводные камни

- Доверять данным клиента — всё валидировать на сервере.
- Хранить состояние в памяти процесса — не масштабируется горизонтально.
- Ловить и «глотать» ошибки без логов.
- Микросервисы на старте проекта — сложность без выгоды; начинать с модульного монолита.
- JWT без срока жизни или без механизма отзыва.
- Не ставить таймауты на внешние запросы — один медленный сервис кладёт всю цепочку.

## Ссылки

- Файлы базы: [проектирование API](../c.patterns/patterns.api-design.md), [backend-паттерны](../c.patterns/patterns.backend.md), [node.auth](../6.node.js/node.auth.md), [node.security](../6.node.js/node.security.md), [стратегия тестирования](../c.patterns/patterns.testing.md), [node.testing](../6.node.js/node.testing.md), [node.observability](../6.node.js/node.observability.md), [node.performance](../6.node.js/node.performance.md), [распределённые паттерны](../c.patterns/patterns.distributed.md)

- Предыдущий: [Базы данных и SQL](roadmap.databases.md) · Следующий: [Паттерны и архитектура](roadmap.patterns.md) → [DevOps](roadmap.devops.md)
- roadmap.sh: [Backend](https://roadmap.sh/backend), [Backend Performance](https://roadmap.sh/best-practices/backend-performance), [System Design](https://roadmap.sh/system-design) · IT Booster: [роадмапы](https://itbooster.ru/roadmap)
- [OWASP Top 10](https://owasp.org/www-project-top-ten/), [The Twelve-Factor App](https://12factor.net/ru/)
