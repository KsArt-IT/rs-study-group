# Роадмап: React

> Теги: roadmap, React, React 19, компоненты, JSX, props, state, хуки, hooks, useState, useEffect, useContext, useMemo, useCallback, кастомные хуки, React Router, state management, Zustand, Redux Toolkit, TanStack Query, формы, React Hook Form, тестирование, Server Components, React Compiler, Feature-Sliced Design, что учить по React
> Основа: roadmap.sh (React), itbooster.ru — Ulbi TV (React) + дополнения. Проверено 2026-10-24.

## Определение

React — библиотека для построения пользовательских интерфейсов из компонентов. UI описывается декларативно как функция от состояния (`UI = f(state)`), React сам вычисляет минимальные изменения DOM (reconciliation). Самый популярный инструмент фронтенда; основа [Next.js](roadmap.nextjs.md) и React Native.

## Зачем / когда использовать

- Перед React — Beginner и Intermediate темы [JavaScript](roadmap.javascript.md). [TypeScript](roadmap.typescript.md) — параллельно.
- Альтернативы: Vue (тоже хороший первый выбор), Angular, Svelte, Solid — в этой базе не разбираются.
- Классовые компоненты устарели, но встречаются в старом коде — достаточно уметь их читать.

## Основное

### 1. Старт и компоненты

- [ ] **J** Создание проекта — Vite (`pnpm create vite`) — см. [настройку репозитория](../b.tools/tools.0-project-setup.md).
- [ ] **J** JSX — выражения, атрибуты (`className`, `htmlFor`), фрагменты.
- [ ] **J** Функциональные компоненты, props, `children`, композиция, дерево компонентов.
- [ ] **J** Классовые компоненты — только знать *(опц.)*.
- [ ] **J** Состояние — `useState`; props vs state; однонаправленный поток данных.
- [ ] **J** Обработка событий.
- [ ] **J** Условный рендеринг, списки и ключи (`key`) — почему не индекс.
- [ ] **J** React DevTools.

### 2. Эффекты, рефы, формы

- [ ] **J** `useEffect` — побочные эффекты, массив зависимостей, cleanup; «You Might Not Need an Effect».
- [ ] **J** Жизненный цикл компонента — монтирование, обновление, размонтирование.
- [ ] **J** `useRef` — доступ к DOM, хранение значения без ререндера; ref как prop (React 19).
- [ ] **J** Контролируемые и неконтролируемые компоненты, работа с формами.
- [ ] **J** Кастомные хуки — вынос логики, правила хуков.
- [ ] **J** `useReducer` — сложное состояние.

### 3. Стили и навигация

- [ ] **J** Стилизация — Tailwind CSS, CSS Modules; UI-библиотеки: shadcn/ui (+ Radix UI), MUI, Chakra UI *(опц.)*.
- [ ] **J** Роутинг — React Router; TanStack Router *(опц.)*.

### 4. Состояние и данные

- [ ] **J** Props drilling → `useContext` (Context API).
- [ ] **J** State management — **Zustand** (самый лёгкий и популярный), **Redux Toolkit** (второй по популярности, крупные проекты); Jotai, MobX, Effector *(опц.)*.
- [ ] **J** Работа с API — `fetch` / axios, загрузка, ошибки, отмена запросов.
- [ ] **J** Server state — **TanStack Query** (кэш, повторные запросы, инвалидация); SWR, RTK Query *(опц.)*; GraphQL-клиенты (Apollo) *(опц.)*.
- [ ] **M** Продвинутые формы — React Hook Form + Zod; Formik *(устаревает)*.

### 5. Производительность

- [ ] **M** Ререндеры — когда и почему компонент перерисовывается; `<StrictMode>`.
- [ ] **M** Мемоизация — `React.memo`, `useMemo`, `useCallback`; **React Compiler** мемоизирует автоматически — ручная мемоизация нужна реже.
- [ ] **M** Lazy components — `React.lazy` + `Suspense`, code splitting.
- [ ] **M** Виртуализация длинных списков — TanStack Virtual.
- [ ] **M** Error Boundary, Portal.

### 6. Тестирование

- [ ] **M** Unit / компонентные — Vitest (или Jest) + React Testing Library; моки сети — MSW.
- [ ] **M** End-to-end — Playwright (рекомендуется), Cypress; WebdriverIO *(опц.)*.

### 7. Продвинутые темы и новые API

- [ ] **M** Concurrent-функции — `useTransition`, `startTransition`, `useDeferredValue`.
- [ ] **M** React 18 — `useId`, `useSyncExternalStore`, `useInsertionEffect` (для авторов библиотек).
- [ ] **M** React 19 — Actions, `useActionState`, `useFormStatus`, `useOptimistic`, `use()`, `<Activity />`, `useEffectEvent`.
- [ ] **M** SSR и Server Components, `<Suspense>` и streaming → подробно в [Next.js](roadmap.nextjs.md).

### 8. Паттерны (все используются в работе)

- [ ] **M** Container / Presentational (UI / Container), Compound Components, Render Props, HOC, Custom Hooks, Slot pattern, Layout composition, Provider pattern, Controlled / Uncontrolled.
- [ ] **M** Общие паттерны → [Паттерны и архитектура](roadmap.patterns.md).

### 9. Теория (собеседования Middle+)

- [ ] **M** Virtual DOM, reconciliation, React Fiber, фазы render и commit, concurrent rendering, hydration, streaming.

### 10. Архитектура frontend

- [ ] **S** Data flow, разделение ответственности, cohesion и coupling.
- [ ] **S** Слоистая и модульная архитектура, **Feature-Sliced Design**, Atomic Design, DDD для фронта.
- [ ] **S** Monorepo ([pnpm workspaces](../b.tools/tools.pnpm.md)), microfrontends *(опц.)*.

### 11. Дальше

- [ ] **M** Анимации — Motion (бывший Framer Motion), `<ViewTransition>` (стабилен с React 19.3) *(опц.)*.
- [ ] **M** Мобильная разработка — React Native + Expo *(опц.)*.

### Чекпоинт

- [ ] SPA с роутингом, авторизацией (mock), Zustand, TanStack Query, формами на React Hook Form + Zod и тестами.

## Подводные камни

- `useEffect` для вычисления производных данных — достаточно посчитать во время рендера ([KISS — derived state](../c.patterns/patterns.kiss.md)).
- Мутация состояния (`state.push(...)`) — React не увидит изменение.
- Индекс массива в качестве `key` при изменяемом списке.
- Всё состояние в глобальном store — локальное состояние держать локально, серверное — в TanStack Query.
- Преждевременная мемоизация везде — сначала измерить (React DevTools Profiler).

## Ссылки

- Файлы базы: [react.effects](../4.react/react.effects.md), [react.performance](../4.react/react.performance.md), [react.testing](../4.react/react.testing.md), [React-паттерны](../c.patterns/patterns.react.md)

- Предыдущий: [TypeScript](roadmap.typescript.md) · Следующий: [Frontend PRO](roadmap.frontend.md) → [Next.js](roadmap.nextjs.md)
- Все темы раздела и файлы: [React: все темы](../4.react/react.0-topics.md)
- roadmap.sh: [React](https://roadmap.sh/react) · IT Booster: [роадмапы](https://itbooster.ru/roadmap)
- [react.dev](https://react.dev/learn)
