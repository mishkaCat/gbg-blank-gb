# gbg-blank-gb — заглушка George Brooks

Статическая страница «Coming soon» для домена **gblegal.ru** (сервер РФ).

## Состав

```
index.html                    единственная страница, без сборки и зависимостей
styles/main.css               оформление
images/logo/logo.svg          логотип George Brooks
images/icons/favicons/        favicon-набор (PNG/ICO/SVG, Apple, Android, MS-tiles)
favicon.ico                   дубль в корне — браузеры запрашивают /favicon.ico сами
site.webmanifest              web app manifest
browserconfig.xml             плитки Windows
robots.txt                    открыт для обхода (индексацию гасит meta robots в index.html)
```

## Развёртывание

Разворачивается bootstrap-скриптом `gbg-inf/scripts/deploy/bootstrap-rf.sh` — обычный
`git clone` в корень статики, Caddy отдаёт файлы напрямую. PHP не нужен: страница
статическая, PHP-кода в ней никогда и не было.

Обновление на сервере:

```bash
sudo -u gbg git -C /srv/www/gblegal pull
```

## Когда приедет gbg-site

1. Убрать из `index.html` строку `<meta name="robots" content="noindex, follow">`.
2. Переключить домен на приложение: `sudo gbg-mode gblegal app`.

Заглушка остаётся на диске и включается обратно одной командой (`gbg-mode gblegal stub`).
