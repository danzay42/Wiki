- `Producer / Publisher`
	Отправляет сообщения в брокер
- `Consumer / Subscriber`
Получает и обрабатывает сообщения из брокера
- `Topic / Exchange / Тема`
Логическая единица, объединяющая сообщения по некоторому принципу

```mermaid
flowchart LR

p(Producer) --> MessageBroker 
subgraph MessageBroker
	direction TB
	q1(Queue)
	q2(Queue)
end
c(Consumer) --> q1

```