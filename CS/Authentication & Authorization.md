-  ***Идентификация*** `(id)?` - процедура определения уникального идентификатора пользователя в информационной системе
- ***Аутентификация*** `(id + key)?` - процедура проверки подлинности пользователя
- ***Авторизация*** `((id + key) + permissions)?` - процедура предоставления прав пользователю

---

# Standards
- SAML
- OpenID 1.0
- OpenID 2.0
- OpenID Connect (OIDC)

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

# Protocols
- OAuth 2.0

# Tokens

## JWT
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