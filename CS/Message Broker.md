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
	p1(Queue)
	p2(Produce)
end

subgraph MessageBroker
	direction TB
	q1(Queue)
	q2(Queue)
end

subgraph Consumer
	direction TB
	q1(Queue)
	q2(Queue)
end

q1 & q2 --- c(Consumer)

```