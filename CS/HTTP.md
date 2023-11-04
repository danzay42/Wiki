**HyperText Transfer Protocol** - Протокол предназначенный для передачи текстовых данных. Расширен для передачи любых [[HTTP#MIME|данных]]

# Запрос
```
$methode $endpoint HTTP/$version
$headers
$body
```
# Ответ
```
HTTP/$version $status_code
$headers
$body
```

# Status Codes

| Code | Meaning                   |
|:---- | ------------------------- |
| 1xx  | Info (не содержат данных) |
| 2xx  | Success                   |
| 3xx  | Redirect                  |
| 4xx  | Client Error              |
| 5xx  | Server Error              |

# MIME
**Multipurpose Internet Mail Extensions** - стандарт, описывающий передачу различных типов данных `multipart/mixed`