# Руководство для разработчиков

## Разработка

Для поддержки нового пункта назначения для данных необходимо разработать модуль
в папке [writer](../../internal/generator/output/general/writer) в `output` слое.

## Тестирование

В качестве инструмента для статического анализа используется linter `golangci-lint`.
Для его запуска можно воспользоваться командой `make test/lint`.
Также есть возможность устранить ошибки статического анализа в автоматическом режиме командой `make test/lint/fix`.

В качестве инструмента для модульного тестирования используются стандартные тесты Go.
Для их запуска можно воспользоваться командой `make test/unit`.

В качестве инструмента для тестирования производительности также используются стандартные тесты Go.
Для их запуска можно воспользоваться командой `make test/performance`.

Для того чтобы посчитать покрытие кода тестами можно воспользоваться командой `make test/cover`.

## Сборка

Для запуска сборки генератора под текущую ОС используется команда `make build`.
Результирующие бинарные файлы будут в папке `build/out`.

## Выпуск релиза

Для выпуска нового релиза необходимо:

1. Проверить и при необходимости исправить список изменений в [CHANGELOG.md](../../CHANGELOG.md).
2. Добавить заголовок для выпускаемой версии со ссылкой на git diff в [CHANGELOG.md](../../CHANGELOG.md) файл.
   Необходимо использовать следующий формат `## [0.0.0](https://.../compare/prev...current) - 2000-12-31`.
3. Сделать коммит в основную ветку (через MR), сообщение которого будет содержать фразу в формате `release 0.0.0`.
