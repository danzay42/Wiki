-  ***Идентификация*** `(id)?` - процедура определения уникального идентификатора пользователя в информационной системе
- ***Аутентификация*** `(id + key)?` - процедура проверки подлинности пользователя
- ***Авторизация*** `((id + key) + permissions)?` - процедура предоставления прав пользователю

```mermaid
flowchart LR
	subgraph Authorization
		direction LR
		subgraph Authentication
			direction LR
			subgraph Identification
				a(ID)
			end
			b(Key)
		end
		c(Permissions)
	end
	a --- b --- c
```

---

# Connection
- session-based
- token-based

# JSON Web Token (JWT)
- **header**
- **payload**
	`json` - объект
- **signature**
	создается на основе секретного ключа информационной системы
```
JWT = base64(header) + "." + base64(payload) + "." + base64(signature)
```

---
# Standards
- SAML 2.0
- OAuth 2.0 -> OAuth 2.1
- OpenID 1.0 -> OpenID 2.0 -> OpenID Connect (OIDC)

```mermaid
flowchart LR
	subgraph OpenID
		A(OAuth)
		B(JWT)
	end
```



## OAuth

### Роли
- **Resource owner**
	*Конечный пользователь*, выдающий согласие *стороннему приложению* ^22176d
- **Client**
	*Стороннее приложение*, запрашивающее доступ у *сервера авторизации*  к *защищенному ресурсу* ^7eff33
- **Resource server**
	*Защищаемый на основе токена ресурс*, с минимальной проверкой токена ^779c29
- **Authorization server**
	*Выделенный сервер* для выдачи токенов после *аутентификации* и *авторизации* ^a90aba

### Учетные данные

Grant type | Client type / Use case
---------- | -
**Authorization code** | Для сторонних приложения, которые могут хранить свой код авторизации в секрете
~~Implicit~~ | Для всех приложений, которые не могут хранить код авторизации в секрете
~~Password~~ | Для доверенных приложений
Client credentials | Для приложений работающих без участия пользователя
Refresh token | Для упрощенного процесса обновления токена
SAML 2.0 bearer | Для перехода с одного защищенного, на основе SAML, домена в другой, на основе OAuth
JWT bearer | Для перехода с одного защищенного, на основе JWT, домена в другой, на основе OAuth 
Device code | Для устройств с ограниченным вводом данных
Token exchange | Для сторонних приложений в случае сценариев делегирования

### Flow

```
		 +--------+                               +---------------+
		 |        |--(A)- Authorization Request ->|   Resource    |
		 |        |                               |     Owner     |
		 |        |<-(B)-- Authorization Grant ---|               |
		 |        |                               +---------------+
		 |        |
		 |        |                               +---------------+
		 |        |--(C)-- Authorization Grant -->| Authorization |
		 | Client |                               |     Server    |
		 |        |<-(D)----- Access Token -------|               |
		 |        |                               +---------------+
		 |        |
		 |        |                               +---------------+
		 |        |--(E)----- Access Token ------>|    Resource   |
		 |        |                               |     Server    |
		 |        |<-(F)--- Protected Resource ---|               |
		 +--------+                               +---------------+
```

```mermaid
sequenceDiagram
	autonumber
	actor o as Resource Owner
	participant c as Client
	participant a as Authorization Server
	participant r as Resource Server

	opt Client Registration
		c ->>+ a: Redirect URL + Client Data
		a ->>- c: ClienID + Secret
	end

	o ->>+ c: Authorization
		c -->>+ a: Redirect to Authorization Server
			a -->>+ o: Authentication
			o ->>- a: Credential
			a ->> a: Check Resource Owner
			a ->>- c: Redirect URL + Code
			c ->>+ a: Code + ClienID + Secret
		a ->>- c: Access + Refresh Token
	c -->>- o: 

	opt
		c ->>+ r: Access Token
		r ->> r: Check Token
		r ->>- c: User Data
	end
```


## WebAuthn

Расширение OAuth, для авторизации с помощью внешних ключей безопасности.

### Роли
![[Authorization#Роли]]
- **Authentication**
	Внешний ключ безопасности
	- генерирует пару открытых / закрытых ключей
	- безопасно хранит закрытый ключ
	- предает открытый ключ
	- подписывает данные закрытым ключом 
- **Relying Party**
	Расширение роли **Authorization server**
- **User Agent**
	Расширение роли **Client**

