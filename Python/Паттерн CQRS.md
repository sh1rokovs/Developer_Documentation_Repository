## Паттерн CQRS
Паттерн CQRS (Command Query Responsibility Segregation) <br />
в&nbsp;Python&nbsp;&mdash; это архитектурный паттерн, который разделяет операции записи (commands) и&nbsp;операции чтения (queries) в&nbsp;приложении.

```Python
# модель данных
class User:
    def __init__(self, name):
        self.name = name
# класс для записи
class UserCommand(Command):
    def execute(self, user):
        user.name = "New Name"
# класс для получения
class UserQuery(Query):
    def execute(self):
        return self.user.name
```
