# Роадмап: Frontend PRO (Junior → Senior)

> Теги: roadmap, frontend, фронтенд, frontend developer, сборщики, Vite, Webpack, линтеры, ESLint, Prettier, Biome, UI-библиотеки, Storybook, тестирование, e2e, производительность, performance, Core Web Vitals, LCP, INP, CLS, Lighthouse, безопасность фронтенда, XSS, CSRF, CORS, деплой фронтенда, Sentry, PWA, сайт медленно грузится, как стать middle frontend
> Основа: roadmap.sh (Frontend, Frontend Performance Best Practices), itbooster.ru — Ulbi TV (Frontend с 0 до PRO) + дополнения. Проверено 2026-10-24.

## Определение

Frontend PRO — всё, что превращает «умею React» в production-уровень: инструменты сборки и качества кода, управление состоянием, тестирование, производительность, безопасность, деплой и мониторинг фронтенда. Роадмап — обзорный: языки и фреймворк вынесены в свои роадмапы, здесь — то, что вокруг них.

## Зачем / когда использовать

- После базы [React](roadmap.react.md). Темы этапа 1 — уровень Junior, этап 2 — Middle, этап 3 — путь к Senior.
- Senior frontend без базовых знаний [Node.js](roadmap.nodejs.md) и [Backend](roadmap.backend.md) не считается полноценным — поэтому дальше маршрут ведёт на бэкенд.

## Основное

### Этап 0. Языки и фреймворк (свои роадмапы)

- [ ] **J** [HTML](roadmap.html.md) → [CSS](roadmap.css.md) → [JavaScript](roadmap.javascript.md) → [TypeScript](roadmap.typescript.md) → [React](roadmap.react.md).
- [ ] **J** Препроцессоры и постпроцессоры — Sass / SCSS, PostCSS (см. [CSS](roadmap.css.md)).

### Этап 1. Инструменты (→ Junior)

- [ ] **J** [Git и GitHub](roadmap.git.md).
- [ ] **J** Пакетные менеджеры — [npm](../b.tools/tools.npm.md), [pnpm](../b.tools/tools.pnpm.md).
- [ ] **J** Работа с API (база) — REST, `fetch`, axios.
- [ ] **J** Сборщики — **Vite** (большинство новых проектов), Turbopack (Next.js), Webpack (много legacy — знать), Rollup / esbuild / Rolldown *(опц.)*.
- [ ] **J** Качество кода — [ESLint](../b.tools/tools.eslint.md), [Prettier](../b.tools/tools.prettier-formatter.md), [Stylelint](../b.tools/tools.stylelint.md); Biome / Oxc — быстрые альтернативы на Rust *(опц.)*; порядок настройки — [чеклист проекта](../b.tools/tools.0-project-setup.md).
- [ ] **J** UI — Tailwind CSS, shadcn/ui, MUI, Chakra UI; Storybook — каталог компонентов.
- [ ] **J** SSR-фреймворк — [Next.js](roadmap.nextjs.md) (Nuxt для Vue, SvelteKit, Astro — *(опц.)*).

### Этап 2. Приложения (→ Middle)

- [ ] **M** Управление состоянием — Zustand / Redux Toolkit; server state — TanStack Query (детали в [React](roadmap.react.md)).
- [ ] **M** Работа с API (продвинуто) — аутентификация и авторизация на клиенте (токены, refresh, cookies), WebSockets, SSE, GraphQL *(опц.)*.
- [ ] **M** Архитектура frontend — классическая, модульная, Feature-Sliced Design, Atomic Design ([Паттерны](roadmap.patterns.md)).
- [ ] **M** Тестирование — unit (Vitest / Jest), компоненты (Testing Library), e2e (Playwright, Cypress), визуальное (Chromatic, Playwright screenshots) *(опц.)*.
- [ ] **Чекпоинт (граница Middle):** несколько законченных проектов с тестами, CI и деплоем, уверенное использование инструментов.

### Этап 3. Production (→ Senior)

- [ ] **M** SEO, семантика и доступность (WCAG 2.2, axe, скринридер).
- [ ] **M** Web-сервер — Nginx (статика, SPA fallback, gzip / brotli, кэш-заголовки); Caddy *(опц.)*.
- [ ] **M** Мониторинг ошибок и аналитика — Sentry (или GlitchTip), Google Analytics / Яндекс Метрика, A/B-тестирование.
- [ ] **M** Производительность — DevTools Performance, Lighthouse, **Core Web Vitals** (LCP, INP, CLS), SSR / SSG (чек-лист ниже).
- [ ] **M** Безопасность — XSS, CSRF, CORS, CSP, clickjacking, безопасные cookies (`HttpOnly`, `Secure`, `SameSite`), rate limiting, зависимости (`npm audit`, Dependabot).
- [ ] **M** CI/CD и релизы — GitHub Actions / GitLab CI, превью-деплои на каждый PR.
- [ ] **M** Деплой — Vercel, Netlify, Cloudflare Pages, GitHub Pages; свой сервер.
- [ ] **S** Docker для фронта — Dockerfile с multi-stage сборкой, Docker Compose → [Docker](roadmap.docker.md).
- [ ] **S** Node.js и Backend → [Node.js](roadmap.nodejs.md).

### Параллельные специализации *(опц.)*

- [ ] PWA и Service Workers · браузерные расширения · десктоп (Electron, Tauri) · мобильная разработка (React Native) · Web Components (Custom Elements, Shadow DOM) · дизайн-системы.

### Чек-лист производительности фронтенда

| Приоритет | Что проверить |
|---|---|
| Высокий | вес страницы < 1500 KB (лучше < 500 KB); загрузка < 3 с; TTFB < 1.3 с; сжатие gzip / brotli; кэш-заголовки HTTP; минификация JS / CSS; `async` / `defer` для скриптов; критический CSS инлайн; сжатые изображения в подходящем формате (WebP / AVIF); HTTPS; нет запросов к 404 |
| Средний | CDN; `width` / `height` у изображений (против CLS); lazy loading изображений вне экрана; размер изображений по размеру показа; SVG вместо растра для иконок; без Base64-картинок; актуальные зависимости; cookie < 4096 байт и < 20 штук |
| Низкий | `preload` / `preconnect` (шрифты); удаление неиспользуемого CSS; WOFF2, шрифты < 300 KB, `font-display: swap` против FOIT; следить за размером зависимостей (Bundlephobia) |
| Инструменты | PageSpeed Insights, Lighthouse, WebPageTest, Chrome DevTools, Bundlephobia, Squoosh |

## Подводные камни

- Подтягивать тяжёлую библиотеку ради одной функции — проверять размер (Bundlephobia).
- Оптимизировать «на глаз» — сначала измерить (Lighthouse, Performance, Web Vitals из реальных пользователей).
- Хранить access-токен в `localStorage` — уязвим к XSS; предпочтительнее `HttpOnly` cookie.
- Учить все сборщики и UI-библиотеки — достаточно Vite + одной UI-библиотеки, остальное по требованию проекта.

## Ссылки

- Файлы базы: [react.testing](../4.react/react.testing.md), [react.performance (Core Web Vitals)](../4.react/react.performance.md), [js.security](../2.js/js.security.md), [frontend-архитектура](../c.patterns/patterns.frontend-architecture.md)

- Предыдущий: [React](roadmap.react.md) · Следующий: [Next.js](roadmap.nextjs.md)
- roadmap.sh: [Frontend](https://roadmap.sh/frontend), [Frontend Performance](https://roadmap.sh/best-practices/frontend-performance) · IT Booster: [роадмапы](https://itbooster.ru/roadmap)
- [web.dev — Core Web Vitals](https://web.dev/articles/vitals)
