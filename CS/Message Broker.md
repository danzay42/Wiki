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
Брокер| Scale | Data Persistent | Клиентские возможности 
--- | --- | --- | --- | ---
Kafka | $> 1e6/s$
RebbitMQ | 
Redis |