-  ***Идентификация*** `(id)?` - процедура определения уникального идентификатора пользователя в информационной системе
- ***Аутентификация*** `(id + key)?` - процедура проверки подлинности пользователя
- ***Авторизация*** `((id + key) + permissions)?` - процедура предоставления прав пользователю

---

# Standards
- SAML 2.0
- OpenID 1.0 -> OpenID 2.0 -> OpenID Connect (OIDC)

```mermaid
flowchart LR
subgraph OpenID Connect
A(OAuth 2.0)
B(JWT)
end
```

## OpenID Flow
- Implicit flow
- Authorization code flow
- Hybrid flow

# OAuth 2.0 (Protocol)

## Роли
- **Resource owner**
	Конечный пользователь, выдающий согласие стороннему приложению
- **Client**
	Стороннее приложение, запрашивающее доступ к защищенному ресурсу
- **Resource server**
	Защищаемый на основе токена ресурс, с минимальной проверкой токена
- **Authorization server**
	Выделенный сервер для выдачи токенов после *аутентификации* и *авторизации*

# JSON Web Token (JWT)
- **header**
- **payload**
	`json` - объект
- **signature**
	создается на основе секретного ключа информационной системы
```
JWT = base64(header) + "." + base64(payload) base64(signature)
```

# Connection
- session-based
- token-based