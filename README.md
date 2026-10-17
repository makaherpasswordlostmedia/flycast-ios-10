# Flycast iOS 10

> Proof of concept: запуск Flycast на 64-битной iOS 10, чтобы показать, что это возможно.

Форк [flycast-ios-restore](https://github.com/themaster567/flycast-ios-restore), который основан на [Flycast](https://github.com/flyinghead/flycast) — мультиплатформенном эмуляторе Sega Dreamcast, Naomi, Naomi 2 и Atomiswave (производный от [reicast](https://github.com/skmp/reicast-emulator)).

> ⚠️ **Статус: экспериментальный.** Это демонстрация возможности, а не стабильный релиз. Возможны баги и вылеты.

## О проекте

Официальный Flycast больше не поддерживает iOS. Этот репозиторий показывает, что эмулятор можно собрать и запустить на устройствах с 64-битной iOS 10.

## Релизы

Актуальный релиз: [**0.1 — iOS 10 64 bit**](https://github.com/makaherpasswordlostmedia/flycast-ios-10/releases/tag/0.1) (pre-release).

Результаты тестирования из заметок к релизу:

| Параметр | Результат |
|----------|-----------|
| Эмулятор | запускается и работает |
| Протестировано на | чип A7 |
| Sonic Adventure | полная скорость |
| Остальные игры | не тестировались |

## Совместимость

- **ОС:** iOS 10 (64-bit)
- **Устройства:** сборка тестировалась на устройстве с чипом A7 (iPhone 5s, iPad Air, iPad mini 2/3 и т.п.)
- Более новые чипы не проверялись, но должны быть не хуже

## Установка

1. Скачайте файл из [релиза 0.1](https://github.com/makaherpasswordlostmedia/flycast-ios-10/releases/tag/0.1) (раздел Assets).
2. Установите его на устройство любым привычным для вас способом.
3. Скопируйте BIOS и образы игр в каталог приложения.

<!-- TODO: уточнить формат файлов в Assets (.ipa / .deb) и способ установки -->

## Использование

Для работы нужны ваши собственные файлы:

- **BIOS** Dreamcast (`dc_boot.bin`, `dc_flash.bin`)
- **Образы игр** (CDI, GDI, CHD и т.д.), полученные из ваших собственных дисков

Проект **не включает** BIOS и игры и не предоставляет ссылок на них.

## Сборка из исходников

```bash
git clone --recursive https://github.com/makaherpasswordlostmedia/flycast-ios-10.git
cd flycast-ios-10
```

Если забыли `--recursive`:

```bash
git submodule update --init --recursive
```

Сборка через CMake (как в upstream):

```bash
mkdir build && cd build
cmake ..
make
```

Доступные пресеты: `cmake --list-presets` (см. `CMakePresets.json`).

<!-- TODO: добавить точный пресет и шаги для iOS-сборки -->

## Структура репозитория

| Путь | Назначение |
|------|------------|
| `core/` | ядро эмулятора |
| `shell/` | платформенный код и оболочки |
| `resources/` | ресурсы приложения |
| `fonts/` | шрифты |
| `intl/` | локализации |
| `tools/` | вспомогательные утилиты |
| `tests/` | тесты |
| `docs/` | документация |
| `CMakeLists.txt`, `CMakePresets.json` | конфигурация сборки |

## Известные ограничения

- Proof of concept — стабильность не гарантируется
- Протестирован только Sonic Adventure, совместимость с остальными играми неизвестна
- Только 64-битные устройства

## Ссылки

- [Upstream Flycast](https://github.com/flyinghead/flycast)
- [Вики Flycast](https://github.com/TheArcadeStriker/flycast-wiki/wiki)
- [Discord Flycast](https://discord.gg/X8YWP8w)
- [flycast-ios-restore](https://github.com/themaster567/flycast-ios-restore)

## Лицензия

См. файл [LICENSE](LICENSE). Проект производный от Flycast и наследует его условия лицензирования.

## Благодарности

- [flyinghead](https://github.com/flyinghead) и все контрибьюторы Flycast
- команда reicast
- [themaster567](https://github.com/themaster567) за flycast-ios-restore

## Отказ от ответственности

Проект не связан с Sega. Dreamcast, Naomi и Atomiswave — торговые марки их владельцев. Используйте только легально полученные BIOS и образы игр.
