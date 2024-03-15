# Проблемы datetime
При работе со сторонними сервисами, с фронтом, со своими сервисами
может возникнуть такая ситуация, что приходящая дата будет в **string** формате
и может быть в разных форматах:
```
2021-11-01 12:34:56.789
2021-11-01 12:34:56
2021-11-01T12:34:56.789
2021-11-01T12:34:56
```
в таком случае обычный подход datetime.strptime(str, format) не подойдет.

Нужно использовать либо такой код:
```Python
def parse_datetime(dt_str):
    formats = [
        "%Y-%m-%d %H:%M:%S.%f",
        "%Y-%m-%d %H:%M:%S",
        "%Y-%m-%dT%H:%M:%S.%f",
        "%Y-%m-%dT%H:%M:%S",
    ]
    for fmt in formats:
        try:
            return datetime.strptime(dt_str, fmt)
        except ValueError:
            pass
    raise ValueError("no valid date format found")
```
Либо библиотеку dateutil (Нужно дополнительно устанавливать)
```Python
from dateutil.parser import parse

date_string = '2021-11-01 12:34:56.789'
date_object = parse(date_string)
```
