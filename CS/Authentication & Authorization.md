-  ***Идентификация*** `(id)?` - процедура определения уникального идентификатора пользователя в информационной системе
- ***Аутентификация*** `(id + key)?` - процедура проверки подлинности пользователя
- ***Авторизация*** `((id + key) + permissions)?` - процедура предоставления прав пользователю

---

Connection
- session-based
- token-based

Standards 
- OpenID
- OAuth
- JWT

# JWT

- header
- payload
	`json` - объект
- signature
	

```
JWT = base64(header).base64(payload).base64(signature)
```