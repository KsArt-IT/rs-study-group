# Роадмап: Node.js

> Теги: roadmap, Node.js, нода, серверный JavaScript, backend на JS, npm, модули, CommonJS, ESM, fs, path, events, EventEmitter, streams, event loop в node, libuv, process.nextTick, http модуль, Express, Fastify, NestJS, Hono, ORM, Prisma, Drizzle, pm2, worker threads, cluster, утечки памяти, что учить по Node.js
> Основа: roadmap.sh (Node.js), itbooster.ru — Ulbi TV (Node JS) + дополнения. Проверено 2026-10-24.

## Определение

Node.js — среда выполнения JavaScript вне браузера на движке V8 с неблокирующим вводом-выводом (библиотека libuv). Подходит для API, real-time-сервисов, CLI-утилит и инструментов разработки. В отличие от браузера, нет DOM и `window`, зато есть доступ к файловой системе, сети и процессам.

## Зачем / когда использовать

- Первый backend для fullstack JS: язык уже знаком. Изучать после [JavaScript](roadmap.javascript.md) (и желательно [TypeScript](roadmap.typescript.md)).
- Этот роадмап — про платформу. API, auth, кэш, очереди, безопасность — в [Backend](roadmap.backend.md); БД — в [Базы данных](roadmap.databases.md).

## Основное

### Beginner — начать с этого

- [ ] **J** Что такое Node.js, зачем, история; Node.js vs браузер (`globalThis`, нет DOM).
- [ ] **J** Установка через [nvm](../b.tools/tools.nvm.md), LTS-версии; запуск `node file.js`, REPL.
- [ ] **J** npm — `package.json`, `node_modules`, локальные и глобальные пакеты, scripts, semver, `npx`, workspaces → [npm](../b.tools/tools.npm.md), [pnpm](../b.tools/tools.pnpm.md).
- [ ] **J** Модули — CommonJS (`require`) и ESM (`import`, `"type": "module"`); `__dirname` / `import.meta.dirname`.
- [ ] **J** TypeScript в Node — запуск `.ts` напрямую (type stripping) или через `tsx`.
- [ ] **J** Core-модули — `process` (`argv`, `env`, `cwd`, `exit`), `os`, `path`, `url`, `fs` (`fs/promises`), `events` (EventEmitter).
- [ ] **J** Переменные окружения — `process.env`, `node --env-file=.env` (без пакета dotenv).
- [ ] **J** Режим разработки — `node --watch`; nodemon *(устаревает)*.

### Асинхронность в Node

- [ ] **J** callbacks (error-first), callback hell, promises, `async / await`, промисифицированные API.
- [ ] **J** Event loop в Node — фазы (timers, poll, check, close), макро- и микрозадачи, `setImmediate` vs `setTimeout`, `process.nextTick`, `queueMicrotask`.

### Intermediate — дальше

- [ ] **J** HTTP — основы протокола, модуль `http`, роутинг вручную, парсинг JSON, REST API → [Backend](roadmap.backend.md).
- [ ] **J** HTTP-запросы из Node — встроенный `fetch`; axios, ky *(опц.)*.
- [ ] **J** Обработка ошибок — типы ошибок (JS, системные, пользовательские, assertion), async-ошибки, `uncaughtException`, `unhandledRejection`, stack trace.
- [ ] **J** Отладка — `node --inspect`, debugger в VS Code / Chrome DevTools.
- [ ] **J** Фреймворки — сначала **Express** (понять основы), затем **NestJS** (основа корпоративной разработки: модули, DI, декораторы); Fastify, Hono *(опц.)*.
- [ ] **J** CLI-приложения — `process.argv`, `stdin` / `stdout` / `stderr`, коды выхода; `node:util.parseArgs` или commander, Inquirer *(опц.)*.
- [ ] **J** Аутентификация — JWT (`jsonwebtoken` / `jose`), Passport.js *(опц.)* → [Backend](roadmap.backend.md).
- [ ] **J** Базы данных — PostgreSQL / MySQL, MongoDB; драйверы (`pg`, `mongodb`), ORM / query builder: **Prisma**, **Drizzle**, TypeORM (NestJS), Mongoose (MongoDB), Knex, Sequelize *(опц.)* → [Базы данных](roadmap.databases.md).
- [ ] **J** Кэш — Redis, Memcached *(опц.)*.
- [ ] **J** Тестирование — Vitest / Jest, встроенный `node:test`, Supertest для API; e2e — Playwright.
- [ ] **J** Логирование — Pino (быстрый, структурированный JSON), Winston, Morgan (HTTP-логи).
- [ ] **M** Шаблонизаторы *(опц.)* — EJS, Pug.

### Advanced — в конце

- [ ] **M** Streams — readable, writable, transform, `pipeline`, backpressure — работа с большими файлами.
- [ ] **M** Production — `NODE_ENV`, graceful shutdown, pm2 (или Docker + оркестратор).
- [ ] **M** Многопоточность — `child_process`, `cluster`, `worker_threads` — когда что.
- [ ] **M** Безопасность платформы — permission model (`--permission`), аудит зависимостей.
- [ ] **S** Теория — libuv и thread pool, паттерн Reactor, глубокое понимание event loop, garbage collector V8.
- [ ] **S** Утечки памяти — heap snapshot, `--inspect`, APM-инструменты.

### Чекпоинты

- [ ] **CLI:** утилита (переименование файлов, парсер CSV → JSON, генератор отчётов).
- [ ] **CRUD API:** Express или NestJS + PostgreSQL + Prisma / Drizzle + валидация Zod + тесты.

## Подводные камни

- Блокировать event loop синхронными операциями (`fs.readFileSync` в обработчике, тяжёлые вычисления) — сервер перестаёт отвечать.
- Необработанный rejected promise — процесс падает.
- Смешивать CommonJS и ESM без понимания — ошибки `require is not defined in ES module scope`, `Cannot use import statement outside a module`.
- Секреты в коде вместо переменных окружения.
- Начинать сразу с NestJS без понимания Express и HTTP — магия декораторов скрывает суть.

## Ссылки

- Файлы базы: [node.auth](../6.node.js/node.auth.md), [node.security](../6.node.js/node.security.md), [node.testing](../6.node.js/node.testing.md), [node.performance](../6.node.js/node.performance.md), [node.observability](../6.node.js/node.observability.md), [backend-паттерны](../c.patterns/patterns.backend.md)

- Предыдущий: [Next.js](roadmap.nextjs.md) · Следующий: [Базы данных и SQL](roadmap.databases.md) → [Backend](roadmap.backend.md)
- Все темы раздела и файлы: [Node.js: все темы](../6.node.js/node.0-topics.md)
- roadmap.sh: [Node.js](https://roadmap.sh/nodejs) · IT Booster: [роадмапы](https://itbooster.ru/roadmap)
- [nodejs.org/docs](https://nodejs.org/docs/latest/api/), [Node.js Learn](https://nodejs.org/en/learn)
