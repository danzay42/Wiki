- `Producer / Publisher`
	Отправляет сообщения в брокер
- `Consumer / Subscriber`
Получает и обрабатывает сообщения из брокера
- `Topic / Exchange / Тема`
Логическая единица, объединяющая сообщения по некоторому принципу

```mermaid
flowchart LR

subgraph Producer
	direction TB
	p1 & p2
end

subgraph MessageBroker
	direction TB
	q1(Queue) & q2(Queue)
end

subgraph Consumer
	direction TB
	c2 & c1
end

p1 -- write --> q1 -- read --> c1
p2 -- write --> q1 & q2 -- read --> c2
```

# Сравнение

[^1]: Количество сообщений в секунду обрабатываемых системой
[^2]: Способность постоянно хранить данные и возможность их восстановить

Брокер | Scale[^1] | Data Persistent[^2] | Клиентские возможности 
--- | --- | --- | ---
[[Message Broker#Kafka\|Kafka]] | > 1e6 | yes | one-to-many
[[Message Broker#RabbitMQ\|RabbitMQ]] | ~ 50e3 | yes/no | one-to-one/one-to-many
[[Message Broker#Redis\|Redis]] | < 1e6 | partial | one-to-one/one-to-many

## Kafka
- Подписчики должны сами забирать сообщение
- Постоянно хранит данные
- Позволяет перечитывать сообщения
- Гарантирует порядок сообщений в топике

## RabbitMQ
- Гибкая маршрутизация
- Удаляет сообщение после доставки
- Сложности при горизонтальном масштабировании
- Гарантирует доставку

## Redis
- В большинстве случаев используется как NoSQL СУБД
- Резервное копирование на определенный момент времени
- Имеет ограниченный функционал по сравнению с другими брокерами

- Обработка больших объемов данных
- Не требуется персистентность
- Необходима
