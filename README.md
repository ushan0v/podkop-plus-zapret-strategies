# Zapret стратегии для Forkop

[![forkop](https://img.shields.io/badge/Forkop-ushan0v-blue)](https://github.com/ushan0v/forkop)
[![zapret-discord-youtube](https://img.shields.io/badge/zapret--discord--youtube-Flowseal-blue)](https://github.com/Flowseal/zapret-discord-youtube/)

Адаптированные NFQWS-стратегии из [Flowseal/zapret-discord-youtube](https://github.com/Flowseal/zapret-discord-youtube/) для [Forkop](https://github.com/ushan0v/forkop).

Источник стратегий: [zapret-discord-youtube/releases/1.9.9d](https://github.com/Flowseal/zapret-discord-youtube/releases/tag/1.9.9d).

## Что внутри

- `discord/` - стратегии для встроенного набора `Discord`.
- `youtube/` - стратегии для встроенного набора  `Youtube`.
- `general/` - универсальные стратегии для остальных доменов/подсетей.
- `assets/` - fake `.bin` файлы, на которые ссылаются стратегии.

Каждый файл стратегии соответствует одному конкретному исходному `.bat` из zapret-discord-youtube.

## Установка assets на OpenWrt

Перед использованием стратегий скачайте fake-файлы из папки `assets/` этого репозитория в каталог zapret:

```sh
d=$(mktemp -d); mkdir -p /opt/zapret/files/fake && wget -qO- https://github.com/ushan0v/forkop-zapret-strategies/archive/refs/heads/main.tar.gz | tar xz -C $d && cp $d/*/assets/*.bin /opt/zapret/files/fake/; rm -rf $d
```

## Как использовать

1. Установите Zapret в Forkop.
2. Создайте отдельную секцию Forkop с действием `Zapret`.
3. Добавьте подходящее условие: `Discord`, `Youtube` или свои домены/подсети.
4. Откройте файл из нужной папки и скопируйте его содержание в поле `Стратегия NFQWS`.

## Как подобрать стратегию

Сначала подберите рабочий `.bat` в оригинальном [Flowseal/zapret-discord-youtube](https://github.com/Flowseal/zapret-discord-youtube/) на той же сети провайдера. Если в оригинальном проекте заработал например `general (ALT11).bat`, то здесь используйте файл с тем же названием и суффиксом `-forkop.txt`.
