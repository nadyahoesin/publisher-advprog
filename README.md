## No 7

a. The publisher program will send five data to the message broker in one run, which are five `UserCreatedEventMessage` instances.

b. The url `amqp://guest:guest@localhost:5672` is the same as in the subscriber program. This is because that is the url of the queue that the publisher send events to and the subscribers receive events from.

## RabbitMQ

![rabbitmq](img/rabbitmq.png)

## Subscriber console

![subscriber console](img/subscriber-console.png)

This is a screen capture of the subscriber console while handling events from the publisher. The events are handled sequentially in the order they were sent (the first five are from the first run of the publisher program, the next five are from the second run).

## Monitoring RabbitMQ

![monitoring rabbitmq](img/monitoring-rabbitmq.png)

This is a screen capture of RabbitMQ after three runs of the publisher program. The first spike is caused by the first two runs of the publisher program as they were done immediately one after the other, and the second spike is caused by the third run of the publisher program. The spike indicates an increase in the rate at which messages are being acknowledged by the subscriber program.