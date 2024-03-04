# Poetry

В качестве пакетного менеджера используется [poetry](https://python-poetry.org/). Конфигурацию определяют 3 файла:

* `pyproject.toml` - основной конфиг для описания зависимостей.
* `poetry.lock` - файл, фиксирующий зависимости
* `setup.cfg` - конфиги, расширяющие описание pyproject.toml

На текущий момент следует использовать версию `poetry==1.8.0`.

1) Установка poetry

```shell
pip install poetry 
```
```shell
pip3 install poetry 
```

2) Установка зависимостей (если в проекте есть файлы - `pyproject.toml` и `poetry.lock`)

```shell
poetry install
```

3) Добавить зависимость в проект

```shell
poetry add <dependency>
```

4) Удаление зависимости (Перед удалением смотрим зависимости, чтобы не рвать связи.)

```shell
poetry remove <dependency>
```

5) Обновление пакета (зависимости)

```shell
poetry update <dependency>
```

6) Инициализация проекта

```shell
poetry my-folder --name my-package
```

7) Если хотим добавить в проект файл только файл `pyproject.toml`

```shell
poetry init
```
