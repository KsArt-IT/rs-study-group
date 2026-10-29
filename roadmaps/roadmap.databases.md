# Роадмап: Базы данных и SQL

> Теги: roadmap, базы данных, БД, database, SQL, PostgreSQL, MySQL, реляционные БД, RDBMS, NoSQL, MongoDB, Redis, DDL, DML, JOIN, GROUP BY, подзапросы, CTE, оконные функции, индексы, транзакции, ACID, нормализация, миграции, ORM, Prisma, Drizzle, репликация, шардирование, pgvector, что учить по SQL, запрос тормозит
> Основа: roadmap.sh (SQL, PostgreSQL DBA, Backend — Databases), itbooster.ru — Ulbi TV (Backend, Node JS) + дополнения. Проверено 2026-10-24.

## Определение

База данных — организованное хранилище данных, СУБД — программа для работы с ним. Реляционные БД (PostgreSQL, MySQL) хранят данные в таблицах со связями и используют язык запросов SQL; NoSQL (документные, key-value, колоночные, графовые) жертвуют частью гарантий ради гибкости схемы или масштабирования.

## Зачем / когда использовать

- После [Node.js](roadmap.nodejs.md), перед [Backend](roadmap.backend.md): почти любой API работает с БД.
- Основная СУБД базы — **PostgreSQL**. SQL учить «руками», а не только через ORM: ORM не спасает от медленных запросов.
- Термины — в [глоссарии БД](../7.db.sql/db.0-terminology.md).

## Основное

### 1. Основы реляционных БД

- [ ] **J** Что такое реляционная БД, преимущества и ограничения; SQL vs NoSQL — когда что.
- [ ] **J** Таблицы, строки, столбцы, схемы; типы данных ([PostgreSQL: типы и подводные камни](../7.db.sql/db.postgresql-pitfalls.md)).
- [ ] **J** Ключи и ограничения — `PRIMARY KEY`, `FOREIGN KEY`, `UNIQUE`, `NOT NULL`, `CHECK`, `DEFAULT`.
- [ ] **J** Связи — один-к-одному, один-ко-многим, многие-ко-многим (связующая таблица).
- [ ] **J** Установка — PostgreSQL в Docker, `psql`, GUI-клиент (DBeaver, pgAdmin, DataGrip).

### 2. SQL — база

- [ ] **J** DDL — `CREATE`, `ALTER`, `DROP`, `TRUNCATE`.
- [ ] **J** DML — `SELECT`, `INSERT`, `UPDATE`, `DELETE`; `WHERE`, `ORDER BY`, `LIMIT` / `OFFSET`, `DISTINCT`.
- [ ] **J** Агрегация — `COUNT`, `SUM`, `AVG`, `MIN`, `MAX`, [GROUP BY и HAVING](../7.db.sql/db.group-by-having.md).
- [ ] **J** JOIN — `INNER`, `LEFT`, `RIGHT`, `FULL OUTER`, self join, cross join.
- [ ] **J** Подзапросы — скалярные, табличные, коррелированные; `EXISTS`, `IN`.
- [ ] **J** Функции — строковые, числовые, даты; `CASE`, `COALESCE`, `NULLIF`; работа с `NULL`.
- [ ] **J** Представления (views).

### 3. Проектирование

- [ ] **J** [Нормальные формы](../7.db.sql/db.normal-forms.md) — 1NF, 2NF, 3NF; когда денормализовать.
- [ ] **J** ER-диаграммы, проектирование схемы под задачу.
- [ ] **J** Миграции — версионирование схемы (Prisma Migrate, Drizzle Kit), откат, миграции без блокировок.

### 4. Транзакции и целостность

- [ ] **J** Транзакции — `BEGIN`, `COMMIT`, `ROLLBACK`, `SAVEPOINT`.
- [ ] **J** ACID; уровни изоляции и аномалии (dirty read, non-repeatable read, phantom).
- [ ] **M** MVCC, блокировки, deadlock; `SELECT ... FOR UPDATE`.
- [ ] **M** Права — `GRANT` / `REVOKE`, роли; Row-Level Security *(опц.)*.

### 5. Производительность

- [ ] **J** Индексы — [общее](../7.db.sql/db.indexes.md), [PostgreSQL](../7.db.sql/db.indexes-postgresql.md), [MySQL](../7.db.sql/db.indexes-mysql.md): B-tree, составные, покрывающие, частичные; GIN, BRIN.
- [ ] **M** План запроса — `EXPLAIN ANALYZE` ([MySQL EXPLAIN](../7.db.sql/db.mysql-explain.md)).
- [ ] **M** Проблема N+1, `SELECT *`, пагинация (keyset вместо `OFFSET`), batch-операции.
- [ ] **M** Пул соединений — PgBouncer, настройки пула в ORM.
- [ ] **M** Slow query log, `pg_stat_statements`, VACUUM.

### 6. Продвинутый SQL

- [ ] **M** CTE (`WITH`), рекурсивные запросы.
- [ ] **M** Оконные функции — `ROW_NUMBER`, `RANK`, `DENSE_RANK`, `LAG`, `LEAD`, `FIRST_VALUE`.
- [ ] **M** `UPSERT` (`ON CONFLICT`), `RETURNING`, `JSONB`.
- [ ] **M** Хранимые процедуры, функции, триггеры *(опц.)*.

### 7. ORM и доступ из кода

- [ ] **J** Зачем ORM, плюсы и минусы; query builder vs ORM.
- [ ] **J** Prisma или Drizzle (TS-first); TypeORM — в NestJS-проектах; Mongoose — для MongoDB.

### 8. NoSQL

- [ ] **J** MongoDB — документы, коллекции, агрегации, индексы.
- [ ] **J** Redis — key-value в памяти: кэш, сессии, очереди, rate limit (→ [Backend](roadmap.backend.md)).
- [ ] **M** Другие типы *(знать, что есть и когда)* — колоночные (ClickHouse, Cassandra, ScyllaDB), поисковые (Elasticsearch, OpenSearch), time series (TimescaleDB, InfluxDB), графовые (Neo4j), embedded (SQLite).
- [ ] **M** Векторный поиск — pgvector в PostgreSQL для AI / RAG → [AI-разработка](roadmap.ai.md).

### 9. Масштабирование (Senior)

- [ ] **S** Репликация — streaming и логическая; read replicas.
- [ ] **S** Шардирование и партиционирование.
- [ ] **S** CAP-теорема, распределённые СУБД (CockroachDB и др.) *(опц.)*.
- [ ] **S** Бэкапы и восстановление — `pg_dump`, `pg_basebackup`, PITR; проверка бэкапов.
- [ ] **S** Управляемые БД в облаке — AWS RDS / Aurora → [AWS](roadmap.aws.md).
- [ ] **S** Мониторинг БД — Prometheus + postgres_exporter, Grafana.

## Подводные камни

- Учить только ORM — не понимать, какой SQL он генерирует, и получать N+1.
- Нет индекса на внешнем ключе и на полях фильтрации — запросы тормозят с ростом данных.
- Индексы «на всё подряд» — замедляют запись.
- Изменение схемы на проде без миграций или с блокирующей миграцией.
- Хранить деньги во `float` — использовать `numeric` / целые копейки.
- Нет бэкапов или бэкапы никогда не проверялись восстановлением.

## Ссылки

- Файлы базы: [транзакции](../7.db.sql/db.transactions.md), [миграции](../7.db.sql/db.migrations.md), [оптимизация и масштабирование](../7.db.sql/db.query-optimization.md), [выбор хранилища](../7.db.sql/db.nosql-overview.md), [доступ к данным](../c.patterns/patterns.data-access.md)

- Предыдущий: [Node.js](roadmap.nodejs.md) · Следующий: [Backend](roadmap.backend.md)
- Все темы раздела и файлы: [Базы данных: все темы](../7.db.sql/db.0-topics.md)
- roadmap.sh: [SQL](https://roadmap.sh/sql), [PostgreSQL DBA](https://roadmap.sh/postgresql-dba) · IT Booster: [роадмапы](https://itbooster.ru/roadmap)
- [PostgreSQL docs](https://www.postgresql.org/docs/current/), [Use The Index, Luke](https://use-the-index-luke.com/)
