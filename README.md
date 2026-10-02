# All in One — каталог модулей

Каталог модулей для [All in One](https://github.com/Solevaral/All-in-one). All in One загружает `catalog.json` при запуске и при проверке обновлений, кэширует его и объединяет со встроенным каталогом: запись с тем же `id` перекрывает встроенную. Записи схемы 2 — для All in One 0.2 и новее.

В каталоге **нет версий** — только где искать модуль. Последнюю версию All in One спрашивает у GitHub Releases репозитория модуля, поэтому менять этот файл нужно только при появлении нового модуля или смене его адреса.

## Как добавить модуль

1. Допишите запись в `modules` в `catalog.json`. Формат и все поля описаны в [docs/MODULES.md](https://github.com/Solevaral/All-in-one/blob/main/docs/MODULES.md).
2. Минимальная версия All in One — в `minHostVersion`: более старые версии покажут запись, но не установят.
3. Программа должна поддерживать режим `--hosted` и протокол HostLink. Готовая реализация для .NET — один файл [HostLink.cs](https://github.com/Solevaral/All-in-one/blob/main/docs/reference/HostLink.cs).

## Фиксы zapret для игр

`zapret-games.json` — галочки карточки «Игры» на странице zapret (All in One 0.2.5 и новее). All in One загружает файл не чаще раза в 6 часов, записи с тем же `id` заменяют встроенные.

| Поле | Смысл |
|---|---|
| `id`, `name` | Идентификатор и название галочки |
| `note` | Подпись под галочкой: что делает, проверено ли |
| `gameFilter` | `all` / `tcp` / `udp` — нужный режим Game Filter |
| `ipset` | `any` («Все адреса») / `loaded` («По списку») |
| `listGeneral` | Домены в `list-general-user.txt` |
| `listExclude` | Домены в `list-exclude-user.txt` |
| `ipsetExclude` | Адреса и подсети в `ipset-exclude-user.txt` |

Снятие галочки убирает только строки, которые она добавила, и возвращает прежние режимы Game Filter и IPSet, если их не меняли вручную.
