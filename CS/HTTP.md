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

Code | Meaning
:-- | ---
1xx | Information (не содержат данных)
2xx | Success
3xx | Redirect
4xx | Client Error
5xx | Server Error