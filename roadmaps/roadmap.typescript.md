# Роадмап: TypeScript

> Теги: roadmap, TypeScript, TS, типизация, статическая типизация, tsconfig, типы, interface vs type, union, intersection, generics, дженерики, narrowing, type guards, utility types, conditional types, mapped types, infer, satisfies, что учить по TypeScript
> Основа: roadmap.sh (TypeScript), itbooster.ru — Ulbi TV (TypeScript) + дополнения. Проверено 2026-10-24.

## Определение

TypeScript — надмножество JavaScript со статической типизацией: типы проверяются на этапе компиляции и стираются, на выходе получается обычный JS. Даёт раннее обнаружение ошибок, автодополнение и безопасный рефакторинг. Типизация — структурная: совместимость определяется формой объекта, а не именем типа.

## Зачем / когда использовать

- Стандарт индустрии для фронта и бэка. Начинать после базы [JavaScript](roadmap.javascript.md) — параллельно с [React](roadmap.react.md) или после его основ.
- Все темы рекомендованы; условные типы и `infer` — сложные, к ним можно вернуться в конце.

## Основное

### 1. Введение

- [ ] **J** Зачем нужен TS; статическая vs динамическая, строгая vs слабая, структурная vs номинальная типизация.
- [ ] **J** TS и JS — совместимость, постепенная миграция, `.d.ts`.
- [ ] **J** TypeScript 7 — компилятор переписан на Go (в 8–12 раз быстрее); старые опции tsconfig из TS 5 удалены.
- [ ] **J** Установка и запуск — `tsc`, `tsx` / `ts-node`, TS Playground; Node.js умеет запускать `.ts` напрямую (type stripping — только стираемый синтаксис, без `enum` и `namespace`).
- [ ] **J** `tsconfig.json` — `strict: true`, `target`, `module`, `moduleResolution`, `noUncheckedIndexedAccess`.
- [ ] **J** Явная типизация и вывод типов (type inference).

### 2. Типы

- [ ] **J** Примитивы — `string`, `number`, `boolean`, `null`, `undefined`, `bigint`, `symbol`.
- [ ] **J** Специальные — `any`, `unknown`, `never`, `void`; top и bottom types.
- [ ] **J** Объектные — `type`, `interface`, массивы, кортежи (tuple), `enum`, классы.
- [ ] **J** Литеральные типы, `as const`.
- [ ] **J** Типы как множества — union `|`, intersection `&`; supertype и subtype; совместимость типов.
- [ ] **J** Поля — `optional ?`, `readonly`.
- [ ] **J** Разница между `type` и `interface` (declaration merging, `extends`).

### 3. Операторы типов и сужение

- [ ] **J** `typeof`, `keyof`, индексные типы `T[K]`.
- [ ] **J** Сужение типов (narrowing) — truthiness, равенство, `typeof`, `instanceof`, `in`, control flow analysis.
- [ ] **J** Type guards (`x is T`), discriminated unions, exhaustive check через `never`.
- [ ] **J** Приведение — `as`, non-null assertion `!`, `satisfies` (проверка без расширения типа).
- [ ] **M** Assertion functions — `asserts x is T`.

### 4. Функции и обобщения

- [ ] **J** Типизация функций — параметры, возвращаемое значение, необязательные параметры, перегрузки (overloads).
- [ ] **J** Generics — обобщённые функции, интерфейсы, классы; ограничения `extends`; значения по умолчанию.
- [ ] **J** Перечисления — `enum`, `const enum` и альтернатива: объект `as const` + union (предпочтительнее).

### 5. ООП в TS

- [ ] **J** Классы — модификаторы доступа (`public`, `private`, `protected`, `#private`), `readonly`, параметры-свойства конструктора.
- [ ] **J** Абстрактные классы, `implements`, наследование, полиморфизм, `static`.
- [ ] **M** Декораторы (стандарт TC39) — нужны в NestJS и Angular *(опц.)*.

### 6. Utility types

- [ ] **J** `Partial`, `Required`, `Readonly`, `Pick`, `Omit`, `Record`.
- [ ] **J** `Exclude`, `Extract`, `NonNullable`.
- [ ] **J** `ReturnType`, `Parameters`, `InstanceType`, `Awaited`.

### 7. Продвинутые типы *(можно вернуться в конце)*

- [ ] **M** Mapped types — `{ [K in keyof T]: ... }`, модификаторы `-readonly`, `?`.
- [ ] **M** Conditional types `T extends U ? X : Y`, `infer`, дистрибутивность.
- [ ] **M** Template literal types, рекурсивные типы.
- [ ] **M** Модули и пространства имён — ES modules, ambient modules, `declare global`, module augmentation.

### 8. Экосистема

- [ ] **J** Типизация данных извне — Zod (схема = источник типа, [DRY](../c.patterns/patterns.dry.md)), Valibot.
- [ ] **J** Линтинг — [typescript-eslint](../b.tools/tools.eslint.md), форматирование — [Prettier](../b.tools/tools.prettier-formatter.md).
- [ ] **M** Сборка — `tsc` только для проверки типов (`--noEmit`), сборка — Vite / esbuild / SWC.
- [ ] **M** TypeScript в React и Node.js → [React](roadmap.react.md), [Node.js](roadmap.nodejs.md).

### 9. Антипаттерны

- [ ] **M** `any` и `@ts-ignore` повсюду (использовать `unknown` и `@ts-expect-error`), избыточная типизация (там, где работает вывод), злоупотребление `enum`, «generic hell» — нечитаемые обобщения, типы `Function` и `Object`.

## Подводные камни

- `strict: false` — половина пользы TS теряется.
- `as` вместо проверки — компилятор молчит, ошибка в рантайме.
- Типы не проверяют данные в рантайме: ответ API нужно валидировать (Zod).
- Считать, что `interface` и `type` полностью взаимозаменяемы.

## Ссылки

- Предыдущий: [Git и GitHub](roadmap.git.md) · Следующий: [React](roadmap.react.md)
- Все темы раздела и файлы: [TypeScript: все темы](../3.ts/ts.0-topics.md)
- roadmap.sh: [TypeScript](https://roadmap.sh/typescript) · IT Booster: [роадмапы](https://itbooster.ru/roadmap)
- [TypeScript Handbook](https://www.typescriptlang.org/docs/handbook/intro.html), [Type Challenges](https://github.com/type-challenges/type-challenges)
