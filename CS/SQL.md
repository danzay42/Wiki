# SQL

## Indexes

- По количеству колонок
   - простой, например, `crete index on table(id)`
   - составной, например, `crete index on table(id, name)`
- По унискальности
   - уникальный, например, `create unique index on table(id)` 
   - неуникальный, например, `create index on table(id)`
- По покрытию строк
   - по всем строкам, например, `create index on table(id)` 
   - по подмножеству, например, `create index on table(id) where deleted_at != null`
- По выражению, например, `create index on table(date(departure_at))`
- Клсастерный индекс
- По структуре данных
   - `B-tree` - поиск по диапазону
   - `Hash-table` - поиск по условию равенства
   - `R-tree` - поиск по координатам
   - ...

## Partitions
Партицирование - разделение одной логической большой таблицы на меньшие физические порции (партиции/секции).
