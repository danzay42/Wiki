
[Architectural Styles and the Design of Network-based Software Architectures](https://www.ics.uci.edu/~fielding/pubs/dissertation/top.htm)

1. Client-Server
2. Stateless
3. Cacheable
4. Uniform interface
5. Layered system
6. Code on demand

```mermaid
flowchart LR
A(Клиенты) <--> B(Транспорт) <--> C(Ресурсы)
```

> Обычно под REST API подразумевают транспорт в виде: [[HTTP]] + JSON

# Best Practice
- конечные точки URL (endpoints) - существительные (ресурсы) ```/resource/{id}```
- множественное число ```/resources```
- документация ([Swagger/OpenAPI](https://swagger.io/))
- версия api указана в пути
- пагинация
- ssl -> tsl
- Правильное использование http-методов
- Правильное использование http-кодов ответов
- принимать/отдавать всегда один и тот же формат упаковки, например json
- сложные запросы ```/resource/{id}/property```

# CRUD + HTTP
- Create - POST
- Read - GET
- Update - PUT
- Delete - DELETE
