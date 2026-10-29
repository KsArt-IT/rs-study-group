# Роадмап: Git и GitHub

> Теги: roadmap, Git, GitHub, GitLab, VCS, контроль версий, version control, коммит, ветки, branch, merge, rebase, pull request, code review, git flow, trunk-based, git hooks, GitHub Actions, что учить по git, как работать в команде с git
> Основа: roadmap.sh (Git and GitHub, Code Review Best Practices), itbooster.ru — Ulbi TV (Git) + дополнения. Проверено 2026-10-24.

## Определение

Git — распределённая система контроля версий (VCS): хранит историю изменений кода, позволяет работать в ветках и объединять работу команды. GitHub (а также GitLab, Bitbucket) — хостинг Git-репозиториев с инструментами совместной работы: Pull Request, code review, issues, CI/CD.

## Зачем / когда использовать

- Начинать сразу после первых проектов на [JavaScript](roadmap.javascript.md) — каждый проект в своём репозитории.
- После блока «База» достаточно для соло-разработки и работы в небольшой команде. Остальное — по мере роста.
- Подробные команды и конфиги — в тематических файлах: [Git](../b.tools/tools.git.md), [GitHub](../b.tools/tools.github.md).

## Основное

### 1. База

- [ ] **J** Что такое VCS и зачем; Git vs другие VCS.
- [ ] **J** Установка, `git config` (global / local): `user.name`, `user.email`, `init.defaultBranch`.
- [ ] **J** Репозиторий — `git init`, `.gitignore`.
- [ ] **J** Как Git устроен внутри — снимки, объекты, ветка как указатель, три дерева ([основы Git](../b.tools/tools.git-basics.md)).
- [ ] **J** Рабочая директория → staging area (index) → коммит: `git status`, `git add`, `git commit`, `git diff`.
- [ ] **J** История — `git log` (опции `--oneline --graph`), `HEAD`.
- [ ] **J** Ветки — создание, переключение (`git switch`), переименование, удаление, слияние (`git merge`).
- [ ] **J** Удалённый репозиторий — аккаунт на GitHub, SSH-ключ, `git remote`, `git clone`, `git fetch`, `git pull`, `git push`.
- [ ] **J** Профиль GitHub — README профиля, pinned-репозитории (портфолио).
- [ ] **Чекпоинт:** выложить свои проекты на GitHub, вести их через ветки.

### 2. Командная работа

- [ ] **J** Fork vs clone, Pull Request (в т.ч. из форка), issues, labels, mentions.
- [ ] **J** Решение конфликтов слияния.
- [ ] **J** Code review — как давать и принимать замечания (см. ниже).
- [ ] **J** Хорошие практики — сообщения коммитов ([commitlint](../b.tools/tools.commitlint.md), Conventional Commits), имена веток, атомарные коммиты, описание PR.
- [ ] **J** Markdown — README проекта, документация.
- [ ] **J** Open source лицензии — MIT, Apache 2.0, GPL *(опц.)*.

### 3. Средний уровень

- [ ] **M** Стратегии слияния — merge (fast-forward vs `--no-ff`), rebase, squash.
- [ ] **M** Отмена изменений — `git restore`, `git reset` (`--soft` / `--mixed` / `--hard`), `git revert`, `git commit --amend`.
- [ ] **M** Работа с историей — `git stash`, `git cherry-pick`, interactive rebase, `git reflog` (спасение «потерянных» коммитов).
- [ ] **M** Переписывание истории и `git push --force-with-lease` (никогда не в общие ветки).
- [ ] **M** Теги и релизы — `git tag`, GitHub Releases, semver.
- [ ] **M** Модели ветвления — GitHub Flow, Git Flow, Trunk-based development, feature branches.
- [ ] **M** Git-хуки — `pre-commit`, `commit-msg`, `pre-push`; [Husky](../b.tools/tools.husky.md) + [lint-staged](../b.tools/tools.lint-staged.md).

### 4. GitHub глубже

- [ ] **M** GitHub Actions — workflow, триггеры, runners, secrets, кэш, артефакты → [GitHub-проверки](../b.tools/tools.github-checks.md).
- [ ] **M** Защита веток — rulesets, required checks, CODEOWNERS, Dependabot, secret scanning ([GitHub-проверки](../b.tools/tools.github-checks.md)).
- [ ] **M** GitHub CLI — `gh pr create`, `gh issue` ([GitHub](../b.tools/tools.github.md)).
- [ ] **M** GitHub Projects — kanban-доски, планирование *(опц.)*.
- [ ] **M** GitHub Pages — деплой статики *(опц.)*.
- [ ] **S** Advanced — `git bisect` (поиск коммита с багом), `git worktree` (несколько веток одновременно — удобно для AI-агентов), submodules, Git LFS, `.gitattributes`.
- [ ] **S** GitHub API, webhooks, GitHub Apps *(опц.)*.
- [ ] **J** GitHub Copilot и AI-ревью PR → [AI-разработка](roadmap.ai.md).

### Code review — чек-лист

Подробно (что смотреть, пирамида, формулировки, Conventional Comments) — [patterns.code-review](../c.patterns/patterns.code-review.md).

| Кто | Что делать |
|---|---|
| Команда | описанный процесс ревью и Definition of Done, общий style guide, автоматизация (линтеры в CI), ожидаемое время ответа |
| Автор до ревью | маленькие PR, само-ревью диффа, тесты (для бага — сначала падающий тест), обновлённая документация, понятное описание и скриншоты |
| Ревьюер | понять требования и контекст, сначала важное (логика, безопасность, производительность), конкретные предложения, мелочи с префиксом `Nit:`, style guide важнее личных вкусов, отмечать хорошее |
| После ревью | автор отвечает на все замечания; разногласия решаются быстро, PR не висит; после merge — проверить в production |

## Подводные камни

- Коммитить секреты (`.env`, ключи) — даже после удаления они остаются в истории.
- `git push --force` в общую ветку — затирает чужую работу.
- Гигантские PR — их невозможно качественно отревьюить.
- Rebase уже опубликованной ветки, над которой работают другие.
- Сообщения коммитов «fix», «update» — история бесполезна.

## Ссылки

- Предыдущий: [JavaScript](roadmap.javascript.md) · Следующий: [TypeScript](roadmap.typescript.md)
- Файлы базы: [Основы Git](../b.tools/tools.git-basics.md), [Git](../b.tools/tools.git.md), [GitHub](../b.tools/tools.github.md), [GitHub-проверки](../b.tools/tools.github-checks.md), [Husky](../b.tools/tools.husky.md), [commitlint](../b.tools/tools.commitlint.md)
- roadmap.sh: [Git and GitHub](https://roadmap.sh/git-github), [Code Review](https://roadmap.sh/best-practices/code-review) · IT Booster: [роадмапы](https://itbooster.ru/roadmap)
- [Pro Git](https://git-scm.com/book/ru/v2)
