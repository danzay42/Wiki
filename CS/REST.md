# REST Architecture
[Architectural Styles and the Design of Network-based Software Architectures](https://www.ics.uci.edu/~fielding/pubs/dissertation/top.htm)

1. Client-Server architecture
2. Stateless
3. [[REST#Cacheable]]
4. [[REST#Uniform interface]]
5. Layered system architecture
6. Code on demand

```mermaid
flowchart LR
A(Клиенты) <--> B(Транспорт) <--> C(Ресурсы)
```

> Обычно под REST API подразумевают транспорт в виде: [[HTTP]] + JSON

# REST API
## Best Practice
- конечные точки URL (endpoints) - существительные (ресурсы) `/resource/{id}`
- множественное число `/resources`
- документация ([Swagger/OpenAPI](https://swagger.io/))
- версия api указана в пути
- пагинация
- ssl -> tsl
- Правильное использование http-методов
- Правильное использование http-кодов ответов
- принимать/отдавать всегда один и тот же формат упаковки, например json
- сложные запросы `/resource/{id}/property`

# Uniform interface

| [[HTTP#Методы\|method]] | URI               | CRUD                          |
| ----------------------- | ----------------- | ----------------------------- |
| POST                    | `/resources`      | создать новый ресурс          |
| GET                     | `/resources/{id}` | получить определенный ресурс  |
| DELETE                  | `/resources/{id}` | удалить ресурс                |
| PUT/PATCH               | `/resources/{id}` | обновить ресурс               |
| GET                     | `/resources`      | получить все доступные ресурс |

# Cacheable
| Кешируемые | Не кешируемые |
| ---------- | ------------- |
| GET        | PUT           |
| POST       | DELETE        |
