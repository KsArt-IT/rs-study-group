# Роадмап: Next.js

> Теги: roadmap, Next.js, Next 16, React-фреймворк, SSR, SSG, ISR, CSR, SPA, стратегии рендеринга, App Router, Pages Router, Server Components, Client Components, Server Actions, кэширование, revalidate, proxy, middleware, metadata, SEO, next/image, Turbopack, деплой Next.js, Vercel, что учить по Next.js
> Основа: roadmap.sh (Next.js), itbooster.ru — Ulbi TV (Next JS) + дополнения. Проверено 2026-10-24.

## Определение

Next.js — fullstack-фреймворк на React: роутинг на основе файлов, серверный рендеринг (SSR), статическая генерация (SSG / ISR), React Server Components, серверные функции (Server Actions) и API-эндпоинты в одном проекте. Решает проблемы SPA — SEO, скорость первой загрузки, работа с данными на сервере.

## Зачем / когда использовать

- После базы [React](roadmap.react.md) (на базовом уровне достаточно, дальше можно учить параллельно). Можно отложить до [Node.js](roadmap.nodejs.md) — тогда серверная часть понятнее.
- Выбор по умолчанию для React-приложений с SEO и серверной логикой. Альтернативы: React Router v7 (framework mode, бывший Remix), TanStack Start, Astro (контентные сайты).

## Основное

### 1. Введение в SSR

- [ ] **J** Стратегии рендеринга — SPA (CSR), SSR, SSG, ISR; плюсы и минусы, когда что.
- [ ] **J** Преимущества SSR — SEO, первая отрисовка, работа с данными на сервере.
- [ ] **J** Первое приложение — `create-next-app`, структура проекта, top-level папки и файлы.

### 2. Роутинг (App Router)

- [ ] **J** App Router vs Pages Router — учить App Router, Pages — знать для старых проектов.
- [ ] **J** Файлы маршрута — `page`, `layout`, `template`, `loading`, `error`, `not-found`.
- [ ] **J** Динамические сегменты `[id]`, catch-all `[...slug]`, route groups `(group)`.
- [ ] **M** Parallel routes `@slot`, intercepting routes `(.)` — модальные окна.
- [ ] **J** Навигация — `<Link>`, `useRouter`, prefetch, redirects.
- [ ] **J** Route Handlers — API-эндпоинты (`route.ts`).
- [ ] **M** Proxy (`proxy.ts`, ранее `middleware.ts`) — редиректы, проверка авторизации, заголовки, cookies, matcher.

### 3. Рендеринг и компоненты

- [ ] **J** Server Components (по умолчанию) vs Client Components (`'use client'`); композиция — где проходит граница.
- [ ] **J** Static vs Dynamic рендеринг; streaming и `<Suspense>`.
- [ ] **M** Runtimes — Node.js и Edge.

### 4. Данные и кэш

- [ ] **J** Загрузка данных на сервере (`async` компонент + `fetch` / ORM) и на клиенте (TanStack Query).
- [ ] **J** Server Actions — мутации из форм (`'use server'`), валидация (Zod), обработка ошибок.
- [ ] **M** Паттерны загрузки — параллельная vs последовательная, preload.
- [ ] **M** Кэширование — Cache Components и `'use cache'`, `cacheLife`, инвалидация `revalidatePath` / `revalidateTag`; мемоизация `fetch`, React `cache()`.
- [ ] **M** Чувствительные данные — `server-only`, не отдавать секреты в Client Components.

### 5. Стили

- [ ] **J** Global CSS, CSS Modules, Tailwind CSS, Sass; CSS-in-JS — ограничения с Server Components.

### 6. Оптимизации и SEO

- [ ] **J** SEO — Metadata API (`metadata`, `generateMetadata`), Open Graph, `robots`, `sitemap`.
- [ ] **J** `next/image`, `next/font`, `next/script`, lazy loading.
- [ ] **M** Аналитика, instrumentation, OpenTelemetry, анализ бандла *(опц.)*.
- [ ] **M** Интернационализация (i18n) *(опц.)*.

### 7. Конфигурация

- [ ] **J** `next.config.ts`, переменные окружения (`NEXT_PUBLIC_*` — попадают в браузер!).
- [ ] **J** TypeScript, ESLint, Prettier.
- [ ] **M** Turbopack (сборщик по умолчанию), Webpack — для старых конфигов; MDX *(опц.)*.

### 8. Тестирование

- [ ] **M** Unit — Vitest / Jest + React Testing Library; e2e — Playwright, Cypress.

### 9. Деплой

- [ ] **J** Vercel — самый простой путь.
- [ ] **M** Node.js-сервер (`next start`), Docker-контейнер (`output: 'standalone'`) → [Docker](roadmap.docker.md), static export, адаптеры для других платформ.

### Чекпоинт

- [ ] Блог или магазин на App Router: Server Components + PostgreSQL через ORM, Server Actions для форм, авторизация (Auth.js / Better Auth), SEO-метаданные, деплой на Vercel и в Docker.

## Подводные камни

- `'use client'` на корневом компоненте — всё дерево уходит в клиентский бандл.
- Ожидать, что данные обновятся, когда они закэшированы — понимать, что и где кэшируется, и как инвалидировать.
- Секреты в переменных с `NEXT_PUBLIC_` — они видны в браузере.
- Вызывать свой Route Handler из Server Component через HTTP — лишний сетевой круг; обращаться к данным напрямую.
- Материалы для Pages Router применять к App Router — API разные.

## Ссылки

- Предыдущий: [Frontend PRO](roadmap.frontend.md) · Следующий: [Node.js](roadmap.nodejs.md)
- Все темы раздела и файлы: [Next.js: все темы](../5.next.js/next.0-topics.md)
- roadmap.sh: [Next.js](https://roadmap.sh/nextjs) · IT Booster: [роадмапы](https://itbooster.ru/roadmap)
- [nextjs.org/docs](https://nextjs.org/docs), [Next.js Learn](https://nextjs.org/learn)
