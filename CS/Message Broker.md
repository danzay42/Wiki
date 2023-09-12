- `Producer / Publisher`
	Отправляет сообщения в брокер
- `Consumer / Subscriber`
Получает и обрабатывает сообщения из брокера
- `Topic / Exchange / Тема`
Логическая единица, объединяющая сообщения по некоторому принципу

```mermaid
flowchart TB

subgraph Producer
	direction TB
	p1
	p2
end

subgraph MessageBroker
	direction TB
	q1(Queue)
	q2(Queue)
end

subgraph Consumer
	direction TB
	c2
	c1
end

Producer --> <essageBrocker

p1 --> q1
p2 --> q1 & q2
c1 --> q1
c2 --> q1 & q2

```