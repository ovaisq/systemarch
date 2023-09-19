In this architecture, the API Gateway receives SCIM requests from clients and forwards them to a load balancer, which distributes the requests to multiple SCIM servers. The SCIM servers interact with the user directory, identity provider, external services, and a database as needed to fulfill SCIM requests. This design enables high availability, scalability, and efficient resource utilization in a complex SCIM system:

``` mermaid
graph TD
  subgraph Clients
    Client1((Client 1))
    Client2((Client 2))
  end
  subgraph APIGateway
    APIGateway1((API Gateway))
  end
  subgraph SCIMServer
    SCIMSrvr((SCIM Server))
  end
  subgraph UserDirectory
    UserDir((User Directory))
  end
  subgraph IdentityProvider
    IdProvider((Identity Provider))
  end
  subgraph ExternalServices
    ExternalService1((External Service 1))
    ExternalService2((External Service 2))
  end
  Client1 -->|SCIM Requests| APIGateway
  Client2 -->|SCIM Requests| APIGateway
  APIGateway -->|"Forwards SCIM 
  Requests"| SCIMServer
  SCIMServer -->|"Queries User
  Data"| UserDirectory
  SCIMServer -->|Authenticates Users| IdentityProvider
  SCIMServer -->|"Accesses External
  Services"| ExternalService1
  SCIMServer -->|"Accesses External
  Services"| ExternalService2
  ```