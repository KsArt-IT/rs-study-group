# Роадмап: Основы WEB

> Теги: roadmap, основы веба, web basics, как работает интернет, how the internet works, HTTP, HTTPS, DNS, домен, хостинг, браузер, клиент-сервер, client-server, frontend vs backend, IDE, VS Code, терминал, что такое frontend, что такое backend, что происходит когда вводишь адрес в браузере
> Основа: roadmap.sh (Frontend, Backend, HTML — Internet), itbooster.ru — Ulbi TV (FullStack, HTML) + дополнения. Проверено 2026-10-24.

## Определение

Основы WEB — минимум знаний о том, как браузер получает и показывает страницу: интернет, DNS, HTTP, сервер, браузер. Это фундамент для frontend и backend: без него непонятно, где выполняется код и почему запрос «не доходит».

## Зачем / когда использовать

- Первый шаг перед [HTML](roadmap.html.md). Глубина — на уровне «могу объяснить, что происходит после ввода URL в браузере».
- К HTTP, кэшированию и безопасности вернуться глубже в [Backend](roadmap.backend.md), к сетям — в [DevOps](roadmap.devops.md).

## Основное

### 1. Как устроен веб

- [ ] **J** Как работает интернет — сети, IP-адрес, пакеты, протоколы TCP/IP на уровне идеи.
- [ ] **J** Доменное имя (domain name) и DNS — как имя превращается в IP-адрес; записи A, CNAME, MX.
- [ ] **J** Хостинг (hosting) — где «живёт» сайт: shared, VPS, облако, статический хостинг.
- [ ] **J** HTTP — запрос и ответ, методы (`GET`, `POST`, `PUT`, `PATCH`, `DELETE`), коды статусов (2xx, 3xx, 4xx, 5xx), заголовки.
- [ ] **J** HTTPS и TLS — зачем шифрование, что такое сертификат.
- [ ] **J** Браузер — как работает: загрузка HTML, построение DOM и CSSOM, рендеринг, выполнение JS ([html.how-browsers-work](../1.html.css/html.how-browsers-work.md)).
- [ ] **J** Что происходит при вводе URL — DNS → TCP/TLS → HTTP-запрос → ответ → рендеринг (классический вопрос на собеседовании).

### 2. Клиент-серверное взаимодействие

- [ ] **J** Клиент и сервер — кто что делает, где выполняется код.
- [ ] **J** Что такое frontend — всё, что видит и с чем взаимодействует пользователь в браузере.
- [ ] **J** Что такое backend — серверная логика, API, БД, интеграции.
- [ ] **J** Как устроены веб-приложения — статический сайт, SPA, SSR; API и JSON как формат обмена.
- [ ] **J** Markup language — что такое язык разметки и чем он отличается от языка программирования.

### 3. Рабочее окружение

- [ ] **J** Редактор / IDE — VS Code (рекомендуется для начала), WebStorm, Cursor (AI-редактор).
- [ ] **J** Браузер и DevTools — вкладки Elements, Console, Network ([tools.chrome-devtools](../b.tools/tools.chrome-devtools.md)).
- [ ] **J** Терминал — `cd`, `ls`, `mkdir`, `cp`, `mv`, `rm`; основы shell (детали — в [DevOps](roadmap.devops.md)).
- [ ] **J** Node.js и версии — установка через [nvm](../b.tools/tools.nvm.md) (понадобится для инструментов уже на этапе CSS/JS).

## Подводные камни

- Пропустить этот блок «потому что скучно» — потом CORS, кэш и cookies кажутся магией.
- Учить сети глубоко на старте — OSI-модель и маршрутизация нужны позже, в [DevOps](roadmap.devops.md).

## Ссылки

- Предыдущий: [Fullstack (старт)](roadmap.0-fullstack.md) · Следующий: [HTML](roadmap.html.md)
- roadmap.sh: [Frontend — Internet](https://roadmap.sh/frontend), [Backend — Internet](https://roadmap.sh/backend)
- MDN: [How the web works](https://developer.mozilla.org/en-US/docs/Learn_web_development/Getting_started/Web_standards/How_the_web_works), [HTTP](https://developer.mozilla.org/en-US/docs/Web/HTTP)
