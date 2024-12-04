Anecdotal to my career, I've noticed that 90% of the small to medium-sized companies I've worked for did not use an API gateway in their SaaS setup. This is because either team lacked expertise, or was not aware of API gateways at all. API gateway offers security benefits, helps manage Microservices complexity, includes out-of-the-box monitoring and analytics are few of many compelling reasons to start with an API Gateway when architecting SaaS platforms. The learning curve for modern API gateways is almost negligible. The presence of an API Gateway would have made several system-level refactors manageable and significantly helped minimize downtime.

This setup is commonly used in microservices architectures to ensure high availability, scalability, and efficient resource utilization. The API Gateway and load balancer play essential roles in managing incoming traffic and distributing it among microservices for processing.

``` mermaid
  graph TD
  subgraph Clients
    Client1((Client 1))
    Client2((Client 2))
    Client3((Client 3))
  end
  subgraph APIGateway
    APIGwy((API Gateway))
  end
  subgraph Microservices
    Microservice1((Microservice 1))
    Microservice2((Microservice 2))
  end
  subgraph LoadBalancer
    LB((Load Balancer))
  end
  subgraph Database
    DB((Database))
  end
  Client1 --> |Requests| APIGateway
  Client2 --> |Requests| APIGateway
  Client3 --> |Requests| APIGateway
  APIGwy --> |Forwards Requests| LoadBalancer
  LB --> |Balances Requests| Microservice1
  LB --> |Balances Requests| Microservice2
  Microservice1 --> |R/W Data| Database
  Microservice2 --> |R/W Data| Database
```
