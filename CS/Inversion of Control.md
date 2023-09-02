---
title: Dependency Injection
tags:
- DI
aliases:
date: 2023-08-07
---

# Dependency Inversion

Before:
```mermaid
flowchart LR
	A --> B
	subgraph pkg1
		A
	end
	subgraph pkg2
		B
	end
```

After:
```mermaid
flowchart LR
	A & B --> IB
	subgraph pkg1
		A; IB
	end
	subgraph pkg2
		B
	end
```


# Dependency Injection

**Внедрение зависимости** (*англ. Dependency injection, DI*) — процесс предоставления внешней зависимости программному компоненту. Является специфичной формой «инверсии управления» (*англ. Inversion of control, IoC*), когда она применяется к управлению зависимостями. В полном соответствии с принципом единственной ответственности объект отдаёт заботу о построении требуемых ему зависимостей внешнему, специально предназначенному для этого общему механизму.
