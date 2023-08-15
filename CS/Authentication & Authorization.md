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

## Учетные данные

Grant type | Client type / Use case
---------- | ----------------------
Authorisation code	Intended for traditional web applications with a backend as well as native (mobile or desktop) applications to take advantage of single sign-on via the system browser.
Implicit	Intended for browser-based (JavaScript) applications without a backend.
Password	For trusted native clients where the application and the authorisation server belong to the same provider.
Client credentials	For clients, such as web services, acting on their own behalf.
Refresh token	A special grant to let clients refresh their access token without having to go through the steps of a code or password grant again.
SAML 2.0 bearer	Lets a client in possession of a SAML 2.0 assertion (sign-in token) exchange it for an OAuth 2.0 access token.
JWT bearer	Lets a client in possession of a JSON Web Token (JWT) assertion from one security domain exchange it for an OAuth 2.0 access token in another domain.
Device	For devices without a browser or with constrained input, such as a smart TV, media console, printer, etc.
Token exchange	Lets applications and services obtain an access token in delegation and impersonation scenarios.

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