# Роадмап: JavaScript

> Теги: roadmap, JavaScript, JS, ECMAScript, ES2025, переменные, типы данных, функции, замыкания, closures, this, прототипы, ООП, DOM, события, асинхронность, promises, async await, event loop, микрозадачи, модули, ESM, что учить по JavaScript, порядок изучения JS
> Основа: roadmap.sh (JavaScript), itbooster.ru — Ulbi TV (JavaScript) + дополнения. Проверено 2026-10-25.

## Определение

JavaScript — язык программирования веба: выполняется в браузере (интерактивность, работа с DOM, запросы к API) и на сервере через [Node.js](roadmap.nodejs.md). Динамически типизированный, однопоточный с неблокирующей асинхронностью через event loop. Стандарт языка — ECMAScript, новая версия выходит ежегодно.

## Зачем / когда использовать

- Главный язык всего стека: фронт, бэк, инструменты. Изучать после [CSS](roadmap.css.md), до [TypeScript](roadmap.typescript.md) и [React](roadmap.react.md).
- Темы разделены на три уровня (как в roadmap.sh): **Beginner → Intermediate → Advanced**. Перед React достаточно Beginner и большей части Intermediate.

## Основное

### Beginner — начать с этого

- [ ] **J** Что такое JS, история, ECMAScript и версии, как запустить (браузер, консоль DevTools, Node.js).
- [ ] **J** Настройка среды — VS Code / WebStorm / Cursor.
- [ ] **J** Переменные — `let`, `const`, `var`; правила имён; hoisting; области видимости (global, function, block) — [js.basics](../2.js/js.basics.md).
- [ ] **J** Типы данных — примитивы (`string`, `number`, `bigint`, `boolean`, `undefined`, `null`, `symbol`) и `object`; `typeof` — [js.core-types](../2.js/js.core-types.md).
- [ ] **J** Преобразование типов — явное и неявное (coercion), truthy / falsy.
- [ ] **J** Операторы — арифметические, унарные (`++x`, `x++`, `+x`), присваивания, сравнения, логические (`&&`, `||`, `!`), тернарный, строковые.
- [ ] **J** Сравнение — `==` vs `===`, `Object.is`, алгоритмы равенства (SameValueZero и др.) *(опц.)*.
- [ ] **J** Условия — `if / else`, `switch / case`, тернарный оператор.
- [ ] **J** Циклы — `for`, `while`, `do...while`, `for...of`, `for...in`, `break` / `continue`.
- [ ] **J** Строки — методы, шаблонные строки (template literals), регулярные выражения — [js.core-strings](../2.js/js.core-strings.md).
- [ ] **J** Числа и даты — точность `0.1 + 0.2`, `Math`, `Date`, `Intl`; Temporal *(опц.)* — [js.core-numbers-dates](../2.js/js.core-numbers-dates.md).
- [ ] **J** Массивы и методы — `map`, `filter`, `reduce`, `find`, `findIndex`, `findLast`, `some`, `every`, `flat`, `flatMap`, `slice`, `splice`, `sort` / `toSorted`; иммутабельные `toSorted`, `toReversed`, `with` — [js.collections-arrays](../2.js/js.collections-arrays.md).
- [ ] **J** Объекты — литералы, деструктуризация, spread `...`, `Object.keys/values/entries`, копирование (shallow / `structuredClone`) — [js.core-objects](../2.js/js.core-objects.md).
- [ ] **J** JSON — `JSON.parse`, `JSON.stringify`.
- [ ] **J** Иммутабельность — почему не мутировать данные (важно для React).

### Функции

- [ ] **J** Function declaration vs expression, стрелочные функции, параметры по умолчанию, `...rest`, `arguments`.
- [ ] **J** Область видимости, лексическое окружение, **замыкания (closures)** — [js.functions-scope-closures](../2.js/js.functions-scope-closures.md).
- [ ] **J** Стек вызовов (call stack), рекурсия.
- [ ] **J** Чистые функции и побочные эффекты — [js.functions-fp](../2.js/js.functions-fp.md).
- [ ] **M** Основы ФП: композиция (`pipe` / `compose`), каррирование и частичное применение, рекурсия, мемоизация — [js.functions-fp](../2.js/js.functions-fp.md).
- [ ] **J** IIFE *(опц.)*, функция-конструктор, strict mode.
- [ ] **J** Ключевое слово `this` — в методе, функции, стрелочной функции, обработчике события; `call`, `apply`, `bind` (на старте можно не углубляться) — [js.functions-this](../2.js/js.functions-this.md).

### Браузер и DOM

- [ ] **J** DOM — поиск элементов (`querySelector`), создание, изменение, удаление, атрибуты и классы — [js.dom](../2.js/js.dom.md).
- [ ] **J** События — `addEventListener`, объект события, всплытие и погружение, делегирование, `preventDefault` — [js.events](../2.js/js.events.md).
- [ ] **J** Формы — чтение значений, `FormData`, валидация.
- [ ] **J** Хранилище — `localStorage`, `sessionStorage`, cookie; IndexedDB *(позже)* — [js.browser-api](../2.js/js.browser-api.md).
- [ ] **M** Observer API — `IntersectionObserver` (lazy load, бесконечная лента), `ResizeObserver`, `MutationObserver`.
- [ ] **M** Drag and Drop *(опц.)*.

### Intermediate — дальше

- [ ] **J** **Асинхронность** — callback, callback hell, `Promise` (`then`, `catch`, `Promise.all / allSettled / race / any`), `async / await` — [js.async](../2.js/js.async.md).
- [ ] **J** **Event loop** — call stack, очередь макрозадач (`setTimeout`, `setInterval`) и микрозадач (промисы, `queueMicrotask`) — очень важная тема для собеседований — [js.event-loop](../2.js/js.event-loop.md).
- [ ] **J** Обработка ошибок — `try / catch / finally`, `throw`, объект `Error`, свои классы ошибок, ошибки в async-коде — [js.errors](../2.js/js.errors.md).
- [ ] **J** Полезные операторы — optional chaining `?.`, nullish coalescing `??`, `??=`.
- [ ] **J** Работа с API — `fetch` (+ `AbortController`), `XMLHttpRequest` (знать), axios — [js.fetch](../2.js/js.fetch.md).
- [ ] **J** ООП — прототипы и прототипное наследование, классы (`class`, `extends`, `super`, `static`, приватные поля `#`), инкапсуляция, наследование, полиморфизм — [js.oop](../2.js/js.oop.md).
- [ ] **J** Модули — ES modules (`import` / `export`), CommonJS (`require`) — знать различия; сборка (Vite, tree shaking, code splitting) — [js.modules-build](../2.js/js.modules-build.md).
- [ ] **J** Тестирование — Jest / Vitest: матчеры, моки, fake timers, async — [js.testing-jest](../2.js/js.testing-jest.md).
- [ ] **M** Коллекции — `Map` / `WeakMap`, `Set` / `WeakSet`; новые методы Set (`union`, `intersection`) — [js.collections-map-set](../2.js/js.collections-map-set.md).
- [ ] **M** Real-time — WebSockets, Server-Sent Events (подробнее в [Backend](roadmap.backend.md)).

### Advanced — в конце

- [ ] **M** Итераторы и генераторы, асинхронные генераторы, `for await...of` — [js.collections-iterators](../2.js/js.collections-iterators.md).
- [ ] **M** Структуры данных на JS — стек, очередь, связный список, хеш-таблица, дерево, граф ([алгоритмы](../e.algorithms/algorithms.0-topics.md): [Big O](../e.algorithms/algorithms.big-o.md), [линейные структуры](../e.algorithms/algorithms.linear-structures.md), [деревья и графы](../e.algorithms/algorithms.trees-and-pathfinding.md)).
- [ ] **M** Метапрограммирование — `Proxy`, `Reflect`, ловушки (traps) — [js.proxy-reflect](../2.js/js.proxy-reflect.md).
- [ ] **M** Бинарные данные — `ArrayBuffer`, `TypedArray`, `DataView` *(опц.)* — [js.binary-data](../2.js/js.binary-data.md).
- [ ] **M** Управление памятью — жизненный цикл, garbage collection, утечки памяти — [js.memory](../2.js/js.memory.md).
- [ ] **M** Web Workers — Dedicated, Shared, Service Worker (PWA, офлайн), Worklets, OffscreenCanvas *(опц.)* — [js.web-workers](../2.js/js.web-workers.md).
- [ ] **M** Отладка в DevTools — breakpoints, Performance, Memory (поиск утечек) ([отладка](../b.tools/tools.chrome-devtools-debugging.md), [производительность](../b.tools/tools.chrome-devtools-performance.md)).
- [ ] **M** Свежие возможности ECMAScript — `Object.groupBy`, `Promise.withResolvers`, `Array.fromAsync`, iterator helpers; *(опц.)* Temporal API для дат — [js.evolution](../2.js/js.evolution.md).

### Чекпоинт

- [ ] Todo-приложение с `localStorage`, погодное приложение на публичном API, игра (крестики-нолики, змейка) — на чистом JS без фреймворков.

## Подводные камни

- Сразу в React без понимания замыканий, `this`, асинхронности и иммутабельности.
- Путать `==` и `===`; полагаться на неявное приведение типов.
- Мутировать массивы (`sort`, `splice`) там, где нужна копия.
- Забывать `await` или `return` в цепочке промисов — ошибки «теряются».
- `var` в новом коде — только `const` по умолчанию и `let` при необходимости.
- Считать, что `setTimeout(fn, 0)` выполнится сразу — сначала выполнятся все микрозадачи.

## Ссылки

- Предыдущий: [CSS](roadmap.css.md) · Следующий: [Git и GitHub](roadmap.git.md) → [TypeScript](roadmap.typescript.md)
- Все темы раздела и файлы: [JavaScript: все темы](../2.js/js.0-topics.md)
- Вопросы к собеседованию: [основы и коллекции](../2.js/js.core-interview.md), [функции](../2.js/js.functions-interview.md), [асинхронность](../2.js/js.async-interview.md), [ООП](../2.js/js.oop-interview.md), [тестирование](../2.js/js.testing-interview.md)
- Связанные: [Node.js](roadmap.nodejs.md), [Паттерны](roadmap.patterns.md)
- roadmap.sh: [JavaScript](https://roadmap.sh/javascript) · IT Booster: [JavaScript](https://itbooster.ru/roadmap/5/)
- [learn.javascript.ru](https://learn.javascript.ru/), [MDN JavaScript](https://developer.mozilla.org/en-US/docs/Web/JavaScript)
