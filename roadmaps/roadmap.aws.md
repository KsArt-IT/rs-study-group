# Роадмап: AWS

> Теги: roadmap, AWS, Amazon Web Services, облако, cloud, IaaS, PaaS, SaaS, IAM, VPC, EC2, S3, SES, Route 53, CloudWatch, CloudFront, RDS, DynamoDB, ElastiCache, ECS, Fargate, EKS, ECR, Lambda, API Gateway, Auto Scaling, ELB, Well-Architected, AWS best practices, большой счёт за AWS, как задеплоить в AWS
> Основа: roadmap.sh (AWS, AWS Best Practices, Full Stack — DevOps), itbooster.ru — Ulbi TV (DevOps — облачные сервисы) + дополнения. Проверено 2026-10-24.

## Определение

AWS (Amazon Web Services) — крупнейший облачный провайдер: вычисления, хранилища, базы данных, сети и сотни других сервисов по модели оплаты за использование. Вместо покупки серверов инфраструктура арендуется и создаётся через консоль, CLI или код ([Terraform](roadmap.terraform.md)).

## Зачем / когда использовать

- После [DevOps](roadmap.devops.md) (Linux, сети) и [Docker](roadmap.docker.md). Сервисов очень много — не нужно знать все: роадмап идёт по шагам от необходимого минимума.
- Лучший способ учить — сделать простое приложение и задеплоить его, используя сервисы из шагов 1–4.
- Альтернативы: Google Cloud, Azure; для простых проектов — PaaS (Vercel, Render, Railway).

## Основное

### Введение

- [ ] **J** Облачные вычисления; IaaS vs PaaS vs SaaS; public / private / hybrid cloud.
- [ ] **J** Глобальная инфраструктура — регионы, зоны доступности (AZ), edge locations.
- [ ] **J** Shared Responsibility Model — за что отвечает AWS, за что — ты.
- [ ] **M** Well-Architected Framework — надёжность, безопасность, производительность, стоимость, операционное совершенство, устойчивость.
- [ ] **J** Аккаунт — root только для настройки (MFA!), **billing alerts / AWS Budgets** сразу; AWS CLI и профили.

### Шаг 1. Основа

- [ ] **J** **IAM** — доступ: пользователи и группы, роли, политики (identity-based и resource-based), instance profiles, assume role, принцип наименьших привилегий; IAM Identity Center (SSO) вместо долгоживущих ключей.
- [ ] **J** **VPC** — сеть: CIDR-блоки, публичные и приватные подсети, route tables, Internet Gateway, NAT Gateway, security groups.
- [ ] **J** **EC2** — вычисления: типы инстансов, CPU credits, тома EBS, key pairs, Elastic IP, user data, варианты покупки (on-demand, reserved / Savings Plans, spot).
- [ ] **M** Масштабирование EC2 — AMI, launch templates, Auto Scaling Groups, scaling policies, Elastic Load Balancer (ALB).

### Шаг 2. Дальше

- [ ] **J** **S3** — хранилище: бакеты и объекты, классы хранения (Standard, IA, Glacier), lifecycle, приватный доступ и presigned URL, статический хостинг.
- [ ] **J** **SES** — отправка почты: sandbox и лимиты, верификация домена, DKIM, обработка bounce / complaint, репутация отправителя.
- [ ] **J** **Route 53** — DNS: hosted zones, записи, ALIAS, routing policies, health checks.
- [ ] **J** **CloudWatch** — мониторинг: метрики, логи, алармы, события.
- [ ] **J** **CloudFront** — CDN: distributions, политики кэширования, invalidations; HTTPS через ACM-сертификат.
- [ ] **Чекпоинт:** фронт в S3 + CloudFront, backend на EC2 за ALB, домен в Route 53, почта через SES.

### Шаг 3. Управляемые сервисы

- [ ] **M** **RDS** — управляемый PostgreSQL / MySQL: инстансы, типы хранилища, бэкапы и восстановление, Multi-AZ, read replicas; Aurora *(опц.)*.
- [ ] **M** **DynamoDB** — NoSQL: таблицы, ключи и вторичные индексы, моделирование данных (single-table design), streams, capacity, DynamoDB Local.
- [ ] **M** **ElastiCache** — управляемый Redis / Valkey / Memcached.
- [ ] **M** **ECR** — registry образов; **ECS** — контейнеры: кластеры, task definitions, services; **Fargate** — без управления серверами.
- [ ] **S** **EKS** — управляемый Kubernetes.

### Шаг 4. Serverless

- [ ] **M** **Lambda** — функции: создание и вызов, layers, runtimes, версии и алиасы, EventBridge и расписания, cold start и лимиты.
- [ ] **M** **API Gateway** — HTTP API перед Lambda; Lambda@Edge / CloudFront Functions *(опц.)*.
- [ ] **M** SQS / SNS — очереди и уведомления *(опц.)*; Secrets Manager / Parameter Store — секреты.
- [ ] **M** Bedrock — LLM-модели в AWS → [AI-разработка](roadmap.ai.md) *(опц.)*.

### Инфраструктура как код

- [ ] **M** Всё созданное руками пересоздать через [Terraform](roadmap.terraform.md) (или AWS CDK).

### Best practices (чек-лист)

| Область | Практика |
|---|---|
| Безопасность | роли IAM для EC2 / Lambda вместо ключей в приложении; права — группам, не пользователям; least privilege; MFA; CloudTrail для аудита; автоматический аудит безопасности; никогда не работать под root |
| Разработка | не хранить состояние на серверах (stateless); официальный SDK; подробные логи и инструменты их просмотра |
| Эксплуатация | автоматизировать всё; думать о сервисе целиком, а не об отдельных серверах; без статических IP у серверов; SSH закрыт (SSM Session Manager); алерты → уведомления |
| Стоимость | детальные billing alerts; reserved / Savings Plans для постоянной нагрузки; удалять неиспользуемые Elastic IP, тома, снапшоты, NAT Gateway |
| EC2 / VPC | теги на всё; termination protection; строгие security groups |
| Надёжность | резервирование по нескольким AZ; health check ELB для Auto Scaling; RDS event subscriptions на failover; знать лимиты сервисов до деплоя |
| Прочее | единая схема именования ресурсов с самого начала; стратегия управления ключами с самого начала; проверить, что AWS подходит под нагрузку |

## Подводные камни

- Нет billing alert — забытый NAT Gateway или крупный инстанс даёт неожиданный счёт.
- Ключи доступа в коде / в Git — боты находят их за минуты.
- Всё в публичной подсети, security group `0.0.0.0/0` на все порты.
- Публичный S3-бакет с приватными данными.
- Всё в одной AZ — сбой зоны кладёт сервис.
- Создавать инфраструктуру только руками в консоли — её невозможно воспроизвести.

## Ссылки

- Предыдущий: [Docker](roadmap.docker.md) · Следующий: [Terraform](roadmap.terraform.md)
- roadmap.sh: [AWS](https://roadmap.sh/aws), [AWS Best Practices](https://roadmap.sh/best-practices/aws)
- [AWS Documentation](https://docs.aws.amazon.com/), [AWS Free Tier](https://aws.amazon.com/free/), [Well-Architected](https://aws.amazon.com/architecture/well-architected/)
