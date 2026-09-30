# All in One — каталог модулей

Каталог модулей для [All in One](https://github.com/Solevaral/All-in-one). All in One загружает `catalog.json` при запуске и при проверке обновлений, кэширует его и объединяет со встроенным каталогом: запись с тем же `id` перекрывает встроенную. Записи схемы 2 — для All in One 0.2 и новее.

В каталоге **нет версий** — только где искать модуль. Последнюю версию All in One спрашивает у GitHub Releases репозитория модуля, поэтому менять этот файл нужно только при появлении нового модуля или смене его адреса.

## Как добавить модуль

1. Допишите запись в `modules` в `catalog.json`. Формат и все поля описаны в [docs/MODULES.md](https://github.com/Solevaral/All-in-one/blob/main/docs/MODULES.md).
2. Минимальная версия All in One — в `minHostVersion`: более старые версии покажут запись, но не установят.
3. Программа должна поддерживать режим `--hosted` и протокол HostLink. Готовая реализация для .NET — один файл [HostLink.cs](https://github.com/Solevaral/All-in-one/blob/main/docs/reference/HostLink.cs).
