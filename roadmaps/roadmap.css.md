# Роадмап: CSS

> Теги: roadmap, CSS, CSS3, стили, вёрстка, селекторы, специфичность, каскад, box model, блочная модель, flexbox, grid, position, адаптивная вёрстка, responsive, media query, container query, анимации, CSS переменные, Tailwind, Sass, BEM, CSS Modules, что учить по CSS, вёрстка едет, элемент не центрируется
> Основа: roadmap.sh (CSS), itbooster.ru — Ulbi TV (CSS, Frontend с 0 до PRO) + дополнения. Проверено 2026-10-25.

## Определение

CSS (Cascading Style Sheets) — язык описания внешнего вида HTML-документа: цвета, шрифты, размеры, раскладка (layout), адаптивность и анимации. «Каскадный» — потому что к элементу применяются правила из разных источников по порядку и специфичности.

## Зачем / когда использовать

- Изучается сразу после [HTML](roadmap.html.md), до [JavaScript](roadmap.javascript.md).
- Главное для Junior — каскад, специфичность, box model, Flexbox, Grid, адаптивность. Препроцессоры, методологии и Tailwind — после базы.

## Основное

### 1. Синтаксис и подключение

Теория: [css.basics](../1.html.css/css.basics.md).

- [ ] **J** Подключение — inline, internal, external CSS; порядок применения.
- [ ] **J** Правило — селектор, свойство, значение (declaration); комментарии.

### 2. Селекторы и каскад

Теория: [css.selectors](../1.html.css/css.selectors.md), [css.cascade](../1.html.css/css.cascade.md).

- [ ] **J** Простые селекторы — по тегу, классу, id, универсальный `*`, группировка.
- [ ] **J** Комбинаторы — потомок (`a b`), прямой ребёнок (`a > b`), соседний брат (`a + b`), все братья (`a ~ b`).
- [ ] **J** Атрибутные селекторы — `[type="text"]`, `[href^="https"]`.
- [ ] **J** Псевдоклассы — `:hover`, `:focus`, `:focus-visible`, `:nth-child()`, `:not()`, `:has()`, `:is()`, `:where()`.
- [ ] **J** Псевдоэлементы — `::before`, `::after`, `::placeholder`.
- [ ] **J** Каскадность, специфичность (0-1-0 и т.д.), наследование, `!important`.
- [ ] **M** Каскадные слои `@layer` — управление порядком стилей без борьбы специфичностей.

### 3. Значения и единицы

Теория: [css.units](../1.html.css/css.units.md), [css.colors](../1.html.css/css.colors.md).

- [ ] **J** Единицы — абсолютные (`px`), относительные (`%`, `em`, `rem`, `vw`, `vh`, `dvh`, `ch`); когда что.
- [ ] **J** Функции — `calc()`, `min()`, `max()`, `clamp()`, `var()`.
- [ ] **J** Цвета — именованные, `hex`, `rgb()`, `hsl()`, `oklch()` (современный стандарт), `opacity`.

### 4. Текст и фон

Теория: [css.typography](../1.html.css/css.typography.md), [css.backgrounds](../1.html.css/css.backgrounds.md).

- [ ] **J** Шрифты — `font-family`, `font-size`, `font-weight`, `line-height`, шорткат `font`, Google Fonts, `@font-face`, WOFF2.
- [ ] **J** Текст — выравнивание, `text-decoration`, `text-transform`, `letter-spacing`, `text-shadow`, `text-overflow`.
- [ ] **J** Фон — `background-color`, `background-image`, градиенты, `background-position`, `background-size`.

### 5. Блочная модель и отображение

Теория: [css.box-model](../1.html.css/css.box-model.md), [css.display](../1.html.css/css.display.md).

- [ ] **J** Box model — `width` / `height`, `padding`, `border`, `margin`, `outline`, схлопывание margin.
- [ ] **J** `box-sizing: border-box` — всегда в reset.
- [ ] **J** `display` — `block`, `inline`, `inline-block`, `none`, `flex`, `grid`; `visibility`.
- [ ] **J** `box-shadow`, `border-radius`.
- [ ] **J** `overflow`, скролл, стилизация scrollbar.

### 6. Позиционирование и раскладка

Теория: [css.position](../1.html.css/css.position.md), [css.flexbox](../1.html.css/css.flexbox.md), [css.grid](../1.html.css/css.grid.md), [css.multicolumn-tables](../1.html.css/css.multicolumn-tables.md).

- [ ] **J** `position` — `static`, `relative`, `absolute`, `fixed`, `sticky`.
- [ ] **J** `z-index` и контекст наложения (stacking context).
- [ ] **J** **Flexbox** — основная одномерная раскладка: оси, `justify-content`, `align-items`, `gap`, `flex: 1`.
- [ ] **J** **Grid** — двумерная раскладка: `grid-template-columns`, `fr`, `repeat()`, `minmax()`, области.
- [ ] **J** `float` — только знать (обтекание текстом), не для раскладки.

### 7. Адаптивность

Теория: [css.responsive](../1.html.css/css.responsive.md).

- [ ] **J** Адаптивный дизайн, резиновая вёрстка, Mobile-first.
- [ ] **J** Media queries — `@media (width >= 768px)`, `prefers-color-scheme`, `prefers-reduced-motion`.
- [ ] **M** Container queries — `@container`: адаптация компонента к размеру родителя.
- [ ] **M** Адаптивная типографика — `clamp()` для размеров шрифта.

### 8. Продвинутое

Теория: [css.custom-properties](../1.html.css/css.custom-properties.md), [css.nesting](../1.html.css/css.nesting.md), [css.animations](../1.html.css/css.animations.md), [css.accessibility](../1.html.css/css.accessibility.md), [css.performance](../1.html.css/css.performance.md), [css.modern](../1.html.css/css.modern.md).

- [ ] **J** CSS-переменные (custom properties) — `--color-primary`, темизация (светлая / тёмная тема).
- [ ] **J** Анимации — `transition`, `transform` (translate, scale, rotate), `@keyframes` + `animation`.
- [ ] **M** 3D-трансформации, `perspective` *(опц.)*.
- [ ] **M** Нативная вложенность (CSS nesting) — `&` прямо в CSS, без препроцессора.
- [ ] **M** Доступность — контраст, видимый фокус, `prefers-reduced-motion`.
- [ ] **M** Производительность — анимировать `transform` и `opacity`, а не `width` / `top`.

### 9. Инструменты и методологии

Теория: [css.methodologies](../1.html.css/css.methodologies.md), [css.tailwind](../1.html.css/css.tailwind.md), [css.sass](../1.html.css/css.sass.md), [css.postcss](../1.html.css/css.postcss.md), [css.in-components](../1.html.css/css.in-components.md).

- [ ] **J** **Tailwind CSS** — utility-first, стандарт в новых React / Next.js проектах.
- [ ] **J** Методология BEM — имена классов `block__element--modifier` ([Clean Code](../c.patterns/patterns.clean-code.md)).
- [ ] **M** Препроцессоры — Sass / SCSS; Less *(опц.)*.
- [ ] **M** Постпроцессоры — PostCSS, Autoprefixer.
- [ ] **M** CSS Modules — локальная область видимости классов в React.
- [ ] **M** CSS-in-JS *(опц.)* — styled-components, Emotion; в проектах с Server Components теряет популярность.
- [ ] **J** Линтер — [Stylelint](../b.tools/tools.stylelint.md).

### 10. Антипаттерны (знать, чтобы не делать)

Теория: [css.antipatterns](../1.html.css/css.antipatterns.md).

- [ ] **M** Избыточные и глубоко вложенные селекторы, `!important` для «победы», магические числа, `float` для раскладки, захардкоженные цвета вместо переменных, «z-index hell» (`z-index: 99999`).

## Подводные камни

- Не понимать специфичность и лечить всё `!important`.
- Забыть `box-sizing: border-box` — ширина «плывёт» из-за padding.
- `z-index` не работает — у элемента `position: static` или он в другом stacking context.
- `100vh` на мобильных прыгает из-за панели браузера — использовать `100dvh`.
- Верстать desktop-first, а потом «чинить» мобильную версию.

## Ссылки

- Предыдущий: [HTML](roadmap.html.md) · Следующий: [JavaScript](roadmap.javascript.md)
- Все темы раздела и файлы: [CSS: все темы](../1.html.css/css.0-topics.md)
- roadmap.sh: [CSS](https://roadmap.sh/css) · IT Booster: [роадмапы](https://itbooster.ru/roadmap)
- MDN: [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS), игры для практики: Flexbox Froggy, Grid Garden
