# Challenges 
- Принимающее приложение может быть не доступно   
- Сеть может быть медленной
- Преодоление множества сетей или фаерволлов
- Различные типы транспортных протоколов

# Структура
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
# Характеристики
- **Message queuing model**: How are messages passed between two parties? (Stream/Queue)
- **Delivery guarantee**: Are messages always delivered at least once, or is this not always the case?
- **Ordering guarantee**
- **Throughput and latency**: How many messages can the platform handle, and how fast is the communication?
- **Persistence and replayability**(постоянство и воспроизводимость): Does the platform store messages and allow for reprocessing if they were missed the first time?

# Сравнение

[^1]: Количество сообщений в секунду обрабатываемых системой
[^2]: Способность постоянно хранить данные и возможность их восстановить

| Брокер                                | Scale[^1] | Data Persistent[^2] | Клиентские возможности |     |
| ------------------------------------- | --------- | ------------------- | ---------------------- | --- |
| [[Message Broker#Kafka\|Kafka]]       | > 1e6     | yes                 | one-to-many            |     |
| [[Message Broker#RabbitMQ\|RabbitMQ]] | ~ 50e3    | yes/no              | one-to-one/one-to-many |     |
| [[Message Broker#Redis\|Redis]]       | < 1e6     | partial             | one-to-one/one-to-many |     |
| NATS                                  |           | no                  |                        |     |

| Message Queuing Model | Delivery Guarantee                        | Ordering Guarantee | Throughput                          | Persistence and Replayability       | Limitations                                                  |
| --------------------- | ----------------------------------------- | ------------------ | ----------------------------------- | ----------------------------------- | ------------------------------------------------------------ |
| NATS                  | At-most-once, At-least-once, Exactly-once | No/Yes             | Up to 3 million messages per second | No/Yes                              | Limited ordering and delivery assurance, limited persistence |
| RabbitMQ              | At-most-once, At-least-once               | Yes                | Up to 60,000 messages per second    | Persistent, but lacks Replayability | Limited scalability, no replayability                        |
| NSQ                   | At-least-once                             | No                 | Up to 800,000 messages per second   | No                                  | Limited scalability and persistence, no replayability        |
| Kafka                 | At-most-once, At-least-once, Exactly-once | Yes                | Up to 2 million messages per second | Yes                                 | Complex setup and management, not suitable for RPCs          |

## Kafka
### Особенности
- Высокая пропускная способность и долговечность
- Подписчики должны сами забирать сообщение
- Постоянно хранит данные
- Позволяет перечитывать сообщения
- Гарантирует порядок сообщений в топике
### Рекомендации
- Обработка больших объемов данных
- При реализации транзакционных или конвертерных систем
- При построении [[Architecture#^725ee5|событийно-ориентированной архитектуры]]
- При использование буфера для логов и метрик
- Сохранность всех сообщений 

## RabbitMQ
[Best Practices](https://www.cloudamqp.com/blog/part1-rabbitmq-best-practice.html)
### Особенности
- Гибкая маршрутизация и долговечность
- Удаляет сообщение после доставки
- Сложности при горизонтальном масштабировании
### Рекомендации
- Нет большого потока данных
- Важна гибкость маршрутизации сообщений
- Важен факт доставки

## Redis
### Особенности
- В большинстве случаев используется как NoSQL СУБД
- Резервное копирование на определенный момент времени
- Имеет ограниченный функционал по сравнению с другими брокерами
### Рекомендации
- Обработка больших объемов данных
- Не требуется персистентность
- Необходима высокая скорость доставки сообщений

## NATS
### Особенности
- Простота конфигурации и развертывания
- Высокая производительность и низкие задержки
### Рекомендации
- взаимодействие между микросервисами
- данные в реальном времени


# Источники
- https://gcore.com/learning/nats-rabbitmq-nsq-kafka-comparison/
- https://pavlo-lompas.medium.com/nats-as-an-alternative-to-kafka-and-rabbitmq-28e5321d5abf
- https://docs.nats.io/nats-concepts/overview/compare-nats