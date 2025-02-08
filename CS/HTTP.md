f**HyperText Transfer Protocol** - Протокол предназначенный для передачи текстовых данных. Расширен для передачи любых [[HTTP#MIME types|данных]]

## Запрос
```shell
$methode $endpoint HTTP/$version
$headers
$body
```
## Ответ
```shell
HTTP/$version $status_code
$headers
$body
```

# Методы
GET - получение ресурса
POST - передача (создание) ресурса
PUT - обновление ресурса
PATCH - частичное обновление ресурса
DELETE - удаление ресурса

# Status Codes
| Code | Meaning                   |
|:----:| ------------------------- |
| 1xx  | Info (не содержат данных) |
| 2xx  | Success                   |
| 3xx  | Redirect                  |
| 4xx  | Client Error              |
| 5xx  | Server Error              |

# Headers

## MIME types
**Multipurpose Internet Mail Extensions** - стандарт, описывающий передачу различных типов данных `multipart/mixed`

# Evolution
| version | description                                        |
| ------- | -------------------------------------------------- |
| 1       | HTTP over TCP                                      |
| 1.1     | "keep-alive" mechanism - reuse same TCP connection |
| 1.1     | (removed) pipelining - parallel requests           |
| 2       | HTTP "streams" - compressed headers                |
| 2       | "subscriptions" - push messages                    |
| 3       | **QUIC** - based on UDP streams                    |
