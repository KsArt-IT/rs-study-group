# Роадмап: DevOps

> Теги: roadmap, DevOps, SRE, Linux, bash, терминал, сети, networking, OSI, TCP/IP, DNS, SSH, Nginx, reverse proxy, load balancer, CI/CD, GitHub Actions, GitLab CI, облака, IaC, Terraform, Ansible, секреты, Vault, мониторинг, Prometheus, Grafana, логи, Loki, Kubernetes, GitOps, ArgoCD, как задеплоить приложение на сервер, как стать devops
> Основа: roadmap.sh (DevOps, DevOps Beginner), itbooster.ru — Ulbi TV (DevOps) + дополнения. Проверено 2026-10-24.

## Определение

DevOps — культура и набор практик, объединяющих разработку (Dev) и эксплуатацию (Ops): автоматизация сборки, тестирования и доставки (CI/CD), инфраструктура как код, мониторинг и быстрая обратная связь. SRE (Site Reliability Engineering) — инженерный подход к надёжности сервисов, близкий к DevOps.

## Зачем / когда использовать

- Для fullstack — после [Backend](roadmap.backend.md): уметь самому задеплоить, обновлять и наблюдать своё приложение. Глубина fullstack — этапы 1–5, для DevOps-инженера — весь роадмап.
- Цепочка: **DevOps (этот файл) → [Docker](roadmap.docker.md) → [AWS](roadmap.aws.md) → [Terraform](roadmap.terraform.md)**. Docker можно изучать сразу после основ Linux.

## Основное

### 1. Язык для автоматизации

- [ ] **J** Любой язык для скриптов: для fullstack — JavaScript / Node.js; в DevOps популярны Python и Go.
- [ ] **J** Bash-скрипты — обязательно.

### 2. Операционные системы и Linux

- [ ] **J** Основы ОС — процессы и потоки, память, CPU, диск, демоны / сервисы.
- [ ] **J** Дистрибутив — Ubuntu / Debian (начинать с Ubuntu); RHEL-семейство, Alpine (в контейнерах) — знать.
- [ ] **J** Терминал — основные команды, файловая система, пайпы и перенаправление вывода, текстовые утилиты (`grep`, `sed`, `awk`, `jq`).
- [ ] **J** Пользователи, root, права (`chmod`, `chown`, `sudo`).
- [ ] **J** Процессы и сервисы — `ps`, `top` / `htop`, `kill`, `systemctl`, `journalctl`.
- [ ] **J** Пакетные менеджеры (`apt`), редакторы `nano` / `vim`.
- [ ] **M** Мониторинг ресурсов — `df`, `du`, `free`, `iostat`, сетевые утилиты (`ss`, `curl`, `dig`, `traceroute`).

### 3. Контроль версий

- [ ] **J** [Git и GitHub](roadmap.git.md); GitLab, Bitbucket — знать. Подход GitOps: любое изменение инфраструктуры — через PR.

### 4. Сети и протоколы

- [ ] **J** Модели OSI и TCP/IP, IP-адресация, подсети (CIDR), порты, маршрутизация, шлюзы.
- [ ] **J** Протоколы — HTTP(S), SSL/TLS, DNS, SSH (ключи, `~/.ssh/config`), FTP / SFTP.
- [ ] **M** Почта — SMTP, IMAP, POP3S; SPF, DKIM, DMARC (чтобы письма не попадали в спам) *(опц.)*.

### 5. Web-серверы и прокси

- [ ] **J** **Nginx** — раздача статики, reverse proxy к Node.js, TLS (Let's Encrypt / certbot), gzip, кэш, rate limiting; Caddy (автоматический HTTPS) *(опц.)*; Apache — знать.
- [ ] **M** Reverse vs forward proxy, load balancer, кэширующий сервер, firewall (`ufw`, security groups).
- [ ] **Чекпоинт — деплой:** приложение на VPS: Node.js + PostgreSQL + Nginx + домен + HTTPS.

### 6. Контейнеры

- [ ] **J** [Docker](roadmap.docker.md) — образы, контейнеры, Dockerfile, Compose. LXC — знать.

### 7. CI/CD

- [ ] **J** Концепции — continuous integration, delivery, deployment; пайплайн: lint → test → build → deploy.
- [ ] **J** Достаточно одного инструмента: **GitHub Actions** ([GitHub-проверки](../b.tools/tools.github-checks.md)) или GitLab CI; Jenkins, CircleCI, TeamCity — знать.
- [ ] **Чекпоинт — CI/CD:** push в `main` → тесты → сборка образа → деплой на сервер.

### 8. Облака

- [ ] **M** Один провайдер глубоко — [AWS](roadmap.aws.md); GCP, Azure, DigitalOcean, Hetzner — знать. РФ-облака — Yandex Cloud, VK Cloud, Selectel.
- [ ] **M** PaaS и serverless — Vercel, Netlify, Cloudflare, Render, Railway; AWS Lambda.
- [ ] **M** Объектное хранилище (S3), сети в облаке, безопасность.

### 9. Инфраструктура как код и конфигурация

- [ ] **M** Provisioning — [Terraform](roadmap.terraform.md) (OpenTofu — открытый форк); Pulumi, AWS CDK, CloudFormation *(опц.)*.
- [ ] **M** Управление конфигурацией — **Ansible** (роли, плейбуки, inventory); Chef, Salt, Puppet — знать.
- [ ] **Чекпоинт — автоматизация:** настройка сервера и бэкап БД одним плейбуком Ansible.

### 10. Секреты

- [ ] **M** Secret management — HashiCorp Vault, SOPS, облачные (AWS Secrets Manager), External Secrets Operator / Sealed Secrets в Kubernetes.

### 11. Мониторинг и логи

- [ ] **M** Мониторинг инфраструктуры — **Prometheus + Grafana**; Zabbix, Datadog *(опц.)*; для старта — Monit / Uptime Kuma.
- [ ] **M** Логи — **Loki** + Promtail / Grafana Alloy или Elastic Stack (ELK); Graylog *(опц.)*.
- [ ] **S** Observability — трейсинг (Jaeger, Tempo), OpenTelemetry; APM (New Relic, Datadog, Dynatrace).
- [ ] **Чекпоинт — мониторинг:** дашборд и алерты в Telegram / Slack о падении и нагрузке.

### 12. Оркестрация (Senior / DevOps-инженер)

- [ ] **S** **Kubernetes** — Pod, Deployment, Service, Ingress, ConfigMap, Secret, Helm; управляемые: EKS / GKE / AKS; AWS ECS / Fargate — проще; Docker Swarm — знать.
- [ ] **S** Хранилища артефактов — Nexus, Artifactory, container registry.
- [ ] **S** GitOps — ArgoCD, FluxCD.
- [ ] **S** Service mesh — Istio, Linkerd, Consul, Envoy *(опц.)*.
- [ ] **S** Cloud design patterns — доступность, управление данными, мониторинг.

## Подводные камни

- Учить Kubernetes раньше Linux, сетей и Docker — без фундамента это набор непонятных YAML.
- Настраивать серверы руками без записи шагов — повторить или восстановить невозможно (решение — IaC и Ansible).
- SSH по паролю и под root — использовать ключи и отдельного пользователя, отключить вход по паролю.
- Нет мониторинга — о падении узнают от пользователей.
- Изучать все CI-системы и облака сразу — достаточно одного инструмента каждого вида.

## Ссылки

- Файлы базы: [стратегии деплоя](../8.devops/devops.deploy-strategies.md), [node.observability](../6.node.js/node.observability.md), [миграции БД](../7.db.sql/db.migrations.md)

- Предыдущий: [Паттерны и архитектура](roadmap.patterns.md) · Следующий: [Docker](roadmap.docker.md)
- roadmap.sh: [DevOps](https://roadmap.sh/devops), [DevOps Beginner](https://roadmap.sh/devops?r=devops-beginner), [Linux](https://roadmap.sh/linux), [Kubernetes](https://roadmap.sh/kubernetes) · IT Booster: [роадмапы](https://itbooster.ru/roadmap)
