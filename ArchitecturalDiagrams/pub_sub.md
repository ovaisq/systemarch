Publishers (Producer 1, Producer 2, Producer 3) are on the left,
representing systems or applications that publish messages to topics.

Kafka Broker (Kafka Broker) is in the middle, serving as the message
broker that receives and stores messages and forwards them to
subscribers based on their topic subscriptions.

Subscribers (Consumer 1, Consumer 2, Consumer 3) are on the right,
representing systems or applications that subscribe to specific 
topics and receive messages from Kafka.

``` mermaid
graph TD
    subgraph Publishers
        p1((Producer 1))
        p2((Producer 2))
        p3((Producer 3))
    end
    subgraph Broker
        kb((Kafka Broker))
    end
    subgraph Subscribers
        c1((Consumer 1))
        c2((Consumer 2))
        c3((Consumer 3))
    end
    p1 --> |Publishes to Topic A| Broker
    p2 --> |Publishes to Topic B| Broker
    p3 --> |Publishes to Topic C| Broker
    Broker --> |Forwards Messages| c1
    Broker --> |Forwards Messages| c2
    Broker --> |Forwards Messages| c3
```
