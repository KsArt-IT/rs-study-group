# Роадмап: Terraform

> Теги: roadmap, Terraform, OpenTofu, IaC, infrastructure as code, инфраструктура как код, HCL, provider, resource, data source, variables, outputs, state, remote state, state locking, modules, workspaces, terraform plan, terraform apply, terraform destroy, Terragrunt, Checkov, tfsec, Trivy, как описать инфраструктуру кодом, руками накликал в консоли
> Основа: roadmap.sh (Terraform, DevOps Beginner, Full Stack — DevOps), itbooster.ru — Ulbi TV (DevOps — инфраструктура как код) + дополнения. Проверено 2026-10-24.

## Определение

Terraform — инструмент инфраструктуры как кода (IaC) от HashiCorp: инфраструктура (серверы, сети, БД, DNS) описывается декларативно на языке HCL, а Terraform сравнивает желаемое состояние с реальным и создаёт / меняет / удаляет ресурсы через API провайдеров (AWS, GCP, Cloudflare и др.). OpenTofu — открытый форк с совместимым синтаксисом.

## Зачем / когда использовать

- Последнее звено цепочки DevOps → [Docker](roadmap.docker.md) → [AWS](roadmap.aws.md) → Terraform. Сначала создать инфраструктуру руками в AWS и понять её, затем удалить и пересоздать через Terraform.
- Даёт воспроизводимость, ревью изменений инфраструктуры через PR, окружения dev / staging / prod из одного кода.
- IaC (создание инфраструктуры) ≠ CaC (настройка серверов — Ansible): обычно используются вместе.

## Основное

### 1. Введение

- [ ] **M** Что такое IaC; IaC vs CaC (configuration as code); сценарии использования и выгоды.
- [ ] **M** Установка; Terraform vs OpenTofu (лицензия BSL vs MPL).

### 2. HCL и провайдеры

- [ ] **M** Синтаксис HCL — блоки, аргументы, выражения, функции.
- [ ] **M** Инициализация проекта — `terraform init`; providers, Terraform Registry, фиксация версий (`required_providers`, `.terraform.lock.hcl`).

### 3. Ресурсы

- [ ] **M** `resource` — поведение и жизненный цикл ресурса.
- [ ] **M** Мета-аргументы — `depends_on`, `count`, `for_each`, `provider`, `lifecycle` (`prevent_destroy`, `create_before_destroy`, `ignore_changes`).
- [ ] **M** Data sources — чтение существующих ресурсов; template files.

### 4. Переменные и выходы

- [ ] **M** Input variables — типы, значения по умолчанию, `*.tfvars`, `TF_VAR_*`, validation rules, `sensitive`.
- [ ] **M** `locals`; outputs (в т.ч. sensitive); preconditions / postconditions.

### 5. Рабочий цикл

- [ ] **M** `terraform fmt`, `terraform validate`, TFLint.
- [ ] **M** `terraform plan` → `terraform apply` → `terraform destroy`; `-replace`.
- [ ] **M** Просмотр — `terraform show`, `output`, `graph`, `state list`.

### 6. State

- [ ] **M** Что такое state и зачем; почему его нельзя терять и коммитить.
- [ ] **M** Remote state — S3-бэкенд с блокировкой (state locking); HCP Terraform.
- [ ] **M** `terraform import` / блок `import` — взять под управление существующие ресурсы.
- [ ] **S** `state mv`, `state rm`, `state pull / push`, `force-unlock`; разделение state на части; версионирование state; чувствительные данные в state.

### 7. Модули

- [ ] **M** Root и child modules; локальные модули; inputs / outputs.
- [ ] **M** Готовые модули из Registry (например, `terraform-aws-modules/vpc`).
- [ ] **S** Best practices модулей — маленькие, переиспользуемые, с фиксированными версиями.

### 8. Provisioners *(знать, использовать редко)*

- [ ] **S** `file`, `local-exec`, `remote-exec`; когда использовать — почти никогда, лучше user data / Ansible / образы.

### 9. Окружения и CI/CD

- [ ] **S** Workspaces vs отдельные директории на окружение.
- [ ] **S** Terraform в CI/CD — GitHub Actions (plan в PR, apply после merge), GitLab CI, Jenkins.
- [ ] **S** Тестирование — `terraform test`, unit / contract / integration / e2e; Terratest *(опц.)*.

### 10. Масштабирование и безопасность

- [ ] **S** Крупные проекты — разделение state, parallelism, Terragrunt.
- [ ] **S** Стоимость — Infracost.
- [ ] **S** Безопасность — секреты не в коде (Vault, AWS Secrets Manager), сканеры Checkov, Trivy (tfsec), KICS, Terrascan; policy as code (Sentinel, OPA) *(опц.)*.
- [ ] **S** HCP Terraform (бывший Terraform Cloud) — удалённые запуски, VCS-интеграция, run tasks *(опц.)*.

### Чекпоинт

- [ ] Описать инфраструктуру из [AWS](roadmap.aws.md): VPC + EC2 / ECS + RDS + S3 + Route 53, remote state в S3, модули, `plan` в PR через GitHub Actions; удалить всё `terraform destroy` и поднять заново.

## Подводные камни

- Локальный state у одного человека — команда не может работать, при потере ноутбука state потерян.
- State в Git — в нём лежат секреты в открытом виде.
- Изменения руками в консоли поверх Terraform (drift) — следующий `apply` их откатит или сломается.
- Не читать `plan` перед `apply` — «destroy» ресурса с данными.
- Версии провайдеров не зафиксированы — обновление ломает конфигурацию.

## Ссылки

- Предыдущий: [AWS](roadmap.aws.md) · Следующий: [AI-разработка](roadmap.ai.md) (или назад к [Fullstack](roadmap.0-fullstack.md))
- roadmap.sh: [Terraform](https://roadmap.sh/terraform)
- [developer.hashicorp.com/terraform](https://developer.hashicorp.com/terraform), [OpenTofu](https://opentofu.org/docs/)
