# Роадмап: Docker

> Теги: roadmap, Docker, контейнеры, containers, контейнеризация, образ, image, Dockerfile, multi-stage build, слои, кэш слоёв, docker run, docker compose, volume, bind mount, сети docker, registry, Docker Hub, GHCR, ECR, безопасность образов, OCI, namespaces, cgroups, у меня работает а на сервере нет, как упаковать приложение в docker
> Основа: roadmap.sh (Docker), itbooster.ru — Ulbi TV (DevOps, Frontend с 0 до PRO; роадмап Docker в разработке) + дополнения. Проверено 2026-10-24.

## Определение

Docker — платформа для упаковки приложения со всеми зависимостями в контейнер: изолированный процесс, который одинаково запускается на ноутбуке, в CI и на сервере. Контейнер создаётся из образа (image), образ описывается в `Dockerfile`. Формат образов стандартизирован (OCI), поэтому они работают и в Podman, и в Kubernetes.

## Зачем / когда использовать

- После основ Linux из [DevOps](roadmap.devops.md). Fullstack-разработчику нужно уверенно: Dockerfile для своего приложения, Docker Compose для локальной среды (app + PostgreSQL + Redis), деплой образа.
- Решает «у меня работает, а на сервере нет», упрощает онбординг и CI.

## Основное

### 1. Введение

- [ ] **J** Что такое контейнер и зачем; bare metal vs виртуальные машины vs контейнеры.
- [ ] **J** Docker и OCI; альтернативы — Podman, containerd *(знать)*.

### 2. Предварительные знания

- [ ] **J** Linux — пакетные менеджеры, пользователи и права, shell-команды и скрипты ([DevOps](roadmap.devops.md)).
- [ ] **J** Архитектура web-приложений — frontend, backend, БД ([Основы WEB](roadmap.web-basics.md)).

### 3. Как это работает *(достаточно общей идеи)*

- [ ] **M** Namespaces (изоляция), cgroups (лимиты ресурсов), union filesystem (слои).

### 4. Установка

- [ ] **J** Docker Desktop (macOS / Windows / Linux) или Docker Engine (Linux); OrbStack / Colima — альтернативы на macOS *(опц.)*.

### 5. Основы

- [ ] **J** Docker CLI — образы (`pull`, `images`, `rmi`), контейнеры (`run`, `ps`, `logs`, `exec`, `stop`, `rm`), `system prune`.
- [ ] **J** Готовые образы — базы данных (`postgres`, `redis`), утилиты в контейнере.
- [ ] **J** Хранение данных — файловая система контейнера эфемерна; volumes и bind mounts.
- [ ] **J** Сети — bridge-сеть, порты (`-p 3000:3000`), связь контейнеров по имени сервиса.
- [ ] **J** Конфигурация запуска — переменные окружения, `--env-file`, лимиты памяти и CPU, restart policy.

### 6. Сборка образов

- [ ] **J** `Dockerfile` — `FROM`, `WORKDIR`, `COPY`, `RUN`, `ENV`, `EXPOSE`, `CMD` vs `ENTRYPOINT`, `.dockerignore`.
- [ ] **J** Кэш слоёв — сначала `package.json` + lock-файл и установка зависимостей, потом код.
- [ ] **M** Multi-stage build — сборка в одном слое, в финальном образе только результат; маленькие базовые образы (`node:*-alpine`, `-slim`, distroless).
- [ ] **M** Размер и безопасность образа — не root (`USER node`), без секретов в слоях, сканирование (Docker Scout, Trivy).

### 7. Registry

- [ ] **J** Docker Hub; GHCR, AWS ECR, GCR и др.
- [ ] **M** Теги — не только `latest`: версия / git SHA; повторяемые сборки.

### 8. Docker Compose

- [ ] **J** `compose.yaml` — сервисы, volumes, сети, `depends_on` + healthcheck, `env_file`; `docker compose up -d`, `logs`, `down`.
- [ ] **J** Локальная среда: app + PostgreSQL + Redis одной командой.

### 9. Developer experience

- [ ] **M** Hot reload (bind mount / Compose Watch), отладчик внутри контейнера, тесты в контейнере, Dev Containers в VS Code *(опц.)*.
- [ ] **M** Docker в CI — сборка и публикация образа в GitHub Actions, кэш сборки (BuildKit, `buildx`), мультиархитектурные образы (amd64 / arm64).

### 10. Безопасность

- [ ] **M** Image security — минимальные образы, обновления, сканирование, подпись образов *(опц.)*.
- [ ] **M** Runtime security — не root, read-only FS, ограничение capabilities, не монтировать `docker.sock`.

### 11. Деплой контейнеров

- [ ] **M** VPS + Docker Compose; PaaS (Render, Railway, Fly.io); AWS ECS / Fargate → [AWS](roadmap.aws.md).
- [ ] **S** Оркестраторы — Kubernetes, Docker Swarm, Nomad → [DevOps](roadmap.devops.md).

### Чекпоинт

- [ ] Fullstack-проект в Docker: multi-stage Dockerfile для frontend (Nginx) и backend (Node.js), Compose с PostgreSQL и Redis, образ собирается в CI и публикуется в GHCR.

## Подводные камни

- `COPY . .` до установки зависимостей — кэш слоёв не работает, каждая сборка ставит всё заново.
- `node_modules` с хоста попадает в образ — нужен `.dockerignore`.
- Данные БД без volume — пропадают при пересоздании контейнера.
- Секреты в `ENV` / `ARG` Dockerfile — остаются в слоях образа.
- `localhost` внутри контейнера — это сам контейнер; к другому сервису обращаться по имени из Compose.
- Образы под arm64 (Apple Silicon) не запускаются на amd64-сервере — собирать с `--platform`.

## Ссылки

- Предыдущий: [DevOps](roadmap.devops.md) · Следующий: [AWS](roadmap.aws.md)
- roadmap.sh: [Docker](https://roadmap.sh/docker) · IT Booster: [роадмапы](https://itbooster.ru/roadmap)
- [docs.docker.com](https://docs.docker.com/), [Dockerfile best practices](https://docs.docker.com/build/building/best-practices/)
