# Индексация postgres
Индексация в PostgreSQL - это механизм оптимизации доступа к данным,<br> 
который позволяет значительно ускорить выполнение запросов к базе данных.<br> 
Индексы создаются на основе одного или нескольких столбцов таблицы и содержат упорядоченные значения этих столбцов,<br> 
которые могут быть быстро проиндексированы и использованы для поиска записей в таблице.<br>

В PostgreSQL существуют несколько типов индексов, включая:

> **B-tree индексы:** наиболее распространенный тип индексов, использующийся для сортировки и поиска значений в столбце. B-tree индексы поддерживают операции поиска, вставки, обновления и удаления записей.
> 
> **Hash индексы:** используются для быстрого поиска значений в столбце по хешу. Hash индексы поддерживают только операции поиска записей, но они значительно быстрее B-tree индексов при большом количестве записей.
> 
> **GiST индексы:** используются для хранения геометрических объектов и поддерживают операции поиска по пространственным критериям.
> 
> **GIN индексы:** используются для хранения текстовых и бинарных значений и поддерживают операции поиска по полнотекстовым критериям.


Индексы в PostgreSQL создаются с помощью команды CREATE INDEX,<br> 
которая принимает имя индекса, таблицу и столбцы, по которым будет создан индекс.<br> 
Например, следующая команда создает B-tree индекс по столбцу last_name таблицы employees:<br>

```SQL
CREATE INDEX idx_employees_last_name ON employees (last_name);
```

Индексы могут значительно ускорить выполнение запросов к базе данных, особенно при большом количестве записей и сложных запросах.<br>
Однако, создание индексов также занимает время и место на диске, поэтому необходимо тщательно продумать, какие индексы создавать и какие нет.<br>

В PostgreSQL также существует возможность создания частичных индексов,<br>
которые индексируют только подмножество записей в таблице, и функциональных индексов,<br>
которые индексируют значения, вычисленные на основе столбцов таблицы.<br>
