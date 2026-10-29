# Роадмап: HTML

> Теги: roadmap, HTML, HTML5, вёрстка, разметка, markup, теги, атрибуты, формы, семантика, semantic tags, accessibility, a11y, доступность, SEO, метатеги, meta, script defer async, что учить по HTML, с чего начать вёрстку
> Основа: roadmap.sh (HTML), itbooster.ru — Ulbi TV (HTML) + дополнения. Проверено 2026-10-25.

## Определение

HTML (HyperText Markup Language) — язык разметки, который описывает структуру и смысл содержимого страницы: заголовки, текст, ссылки, формы, медиа. Браузер строит из HTML дерево DOM, а CSS и JavaScript работают уже с ним.

## Зачем / когда использовать

- Первый язык после [Основ WEB](roadmap.web-basics.md). Изучается быстро, но семантика, формы и доступность нужны на всех уровнях.
- Атрибутов и тегов очень много — заучивать всё на старте не нужно, важны часто используемые.

## Основное

### 1. Первый документ

Теория: [html.document](../1.html.css/html.document.md).

- [ ] **J** Первый HTML-файл — `index.html`, открыть в браузере, Live Server в VS Code.
- [ ] **J** Структура документа — `<!DOCTYPE html>`, `<html lang>`, `<head>`, `<body>`, `<title>`, `<meta charset>`.
- [ ] **J** Комментарии `<!-- -->`, регистр тегов (нечувствителен), пробелы и переносы (схлопываются).
- [ ] **J** Виды тегов — парные / одиночные (void), блочные / строчные.

### 2. Текст и контейнеры

Теория: [html.text](../1.html.css/html.text.md), [html.attributes](../1.html.css/html.attributes.md).

- [ ] **J** Текстовые теги — `h1`…`h6`, `p`, `br`, `hr`, `pre`, `b` / `strong`, `i` / `em`, `mark`, `sub`, `sup`.
- [ ] **J** Цитаты и правки *(опц.)* — `blockquote`, `q`, `cite`, `abbr`, `dfn`, `address`, `del`, `ins`, `s`.
- [ ] **J** HTML-сущности (entities) — `&lt;`, `&amp;`, `&nbsp;`.
- [ ] **J** Контейнеры — `div` (блочный), `span` (строчный).
- [ ] **J** Атрибуты — `class`, `id`, `style`, `data-*`, глобальные (standard) атрибуты.

### 3. Ссылки, списки, таблицы

Теория: [html.links](../1.html.css/html.links.md), [html.lists-tables](../1.html.css/html.lists-tables.md).

- [ ] **J** Ссылки `<a>` — `href` (абсолютный, относительный, якорь `#id`, `mailto:`), `target="_blank"` + `rel="noopener"`.
- [ ] **J** Списки — нумерованный `ol`, маркированный `ul`, список определений `dl`, вложенные списки.
- [ ] **J** Таблицы — `table`, `thead`, `tbody`, `tr`, `th`, `td`, `colspan` / `rowspan`; только для табличных данных, не для раскладки.

### 4. Формы

Теория: [html.forms](../1.html.css/html.forms.md), [html.form-validation](../1.html.css/html.form-validation.md).

- [ ] **J** `<form>`, `action`, `method`, `submit`.
- [ ] **J** Контролы — `input` (text, email, password, number, radio, checkbox, file, date), `textarea`, `select`, `button`.
- [ ] **J** `label` и связь с `input` (`for` / вложение) — обязательно для доступности.
- [ ] **J** Встроенная валидация — `required`, `pattern`, `min` / `max`, `minlength`; её ограничения (серверная проверка обязательна).
- [ ] **J** Загрузка файлов — `enctype="multipart/form-data"`.
- [ ] **J** События формы — `submit`, `input`, `change` (подробно в [JavaScript](roadmap.javascript.md)).

### 5. Медиа и встраивание

Теория: [html.images](../1.html.css/html.images.md), [html.media](../1.html.css/html.media.md).

- [ ] **J** `img` — `src`, `alt` (обязателен), `width` / `height` (против сдвига макета), `loading="lazy"`.
- [ ] **J** `img` vs `figure` + `figcaption`; `picture` и `srcset` для адаптивных изображений.
- [ ] **J** `audio`, `video`, `iframe`.
- [ ] **M** Priority Hints — `fetchpriority`, `preload` *(позже)*.

### 6. Семантика, доступность, SEO

Теория: [html.semantics](../1.html.css/html.semantics.md), [html.accessibility](../1.html.css/html.accessibility.md), [html.interactive](../1.html.css/html.interactive.md), [html.seo](../1.html.css/html.seo.md).

- [ ] **J** Семантические теги — `header`, `nav`, `main`, `section`, `article`, `aside`, `footer`.
- [ ] **J** Доступность (accessibility, a11y) — семантика вместо `div`, `alt`, `label`, порядок заголовков, работа с клавиатуры, базовые ARIA-атрибуты; ориентир — WCAG 2.2.
- [ ] **J** Метатеги — `viewport`, `description`, Open Graph (`og:*`) для превью в соцсетях.
- [ ] **J** Основы SEO — `title`, `description`, иерархия заголовков, семантика, `robots`, `sitemap.xml`.

### 7. Подключение CSS и JS

Теория: [html.resources](../1.html.css/html.resources.md), [html.security](../1.html.css/html.security.md), [html.how-browsers-work](../1.html.css/html.how-browsers-work.md), [html.web-components](../1.html.css/html.web-components.md).

- [ ] **J** Стили — inline, internal (`<style>`), external (`<link rel="stylesheet">`) → [CSS](roadmap.css.md).
- [ ] **J** `<script>` — `src`, `defer`, `async`, `type="module"`; почему скрипты в конце или с `defer`.
- [ ] **M** CSP (Content Security Policy) — ограничение источников скриптов *(позже, см. [Backend](roadmap.backend.md))*.

### Инструменты

- [ ] **J** Линтер HTML — [html-eslint](../b.tools/tools.html-eslint.md), форматирование — [Prettier](../b.tools/tools.prettier-formatter.md).

## Подводные камни

- Вёрстка на `div` без семантики — плохо для SEO и доступности.
- `alt` пропущен или заполнен «image» — для скринридера картинки нет.
- Таблицы для раскладки страницы — устаревший подход, раскладка делается CSS (Flexbox, Grid).
- `<br>` для отступов вместо CSS.
- Полагаться только на HTML-валидацию формы — её легко обойти, проверка на сервере обязательна.

## Ссылки

- Предыдущий: [Основы WEB](roadmap.web-basics.md) · Следующий: [CSS](roadmap.css.md)
- Все темы раздела и файлы: [HTML: все темы](../1.html.css/html.0-topics.md)
- Связанные: [Clean Code — HTML/CSS code style](../c.patterns/patterns.clean-code.md)
- roadmap.sh: [HTML](https://roadmap.sh/html) · IT Booster: [HTML](https://itbooster.ru/roadmap/11/)
- MDN: [HTML](https://developer.mozilla.org/en-US/docs/Web/HTML), [Accessibility](https://developer.mozilla.org/en-US/docs/Web/Accessibility)
