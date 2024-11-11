In this architecture, the API Gateway receives SCIM requests from clients and forwards them to a load balancer, which distributes the requests to multiple SCIM servers. The SCIM servers interact with the user directory, SAML 2.0 Identity Provider, external services, and a database as needed to fulfill SCIM requests. This design enables high availability, scalability, and efficient resource utilization in somewhat of a complex SCIM system using SAML 2.0 for authentication:

```mermaid
flowchart TD
  subgraph Clients
    Client1((Client 1))
    Client2((Client 2))
  end
  subgraph APIGateway
    KongHQ((API Gateway))
  end
  subgraph LoadBalancer
    LB((Load Balancer))
  end
  subgraph SCIMServer1
    SCIMSrvr1((SCIM Server 1))
  end
  subgraph SCIMServer2
    SCIMSrvr2((SCIM Server 2))
  end
  subgraph UserDirectory
    UserDir((User Directory))
  end
  subgraph IdentityProvider
    IdProvider((SAML 2.0))
  end
  subgraph ExternalServices
    ExternalService1((External Service 1))
    ExternalService2((External Service 2))
  end
  subgraph Database
    DB((Database))
  end

  Client1 -->|SCIM Requests| APIGateway
  Client2 -->|SCIM Requests| APIGateway
  APIGateway -->|Load Balancing| LoadBalancer
  LoadBalancer -->|Distributes Requests| SCIMServer1
  LoadBalancer -->|Distributes Requests| SCIMServer2
  SCIMServer1 -->|"Queries User
Data"| UserDirectory
  SCIMServer1 -->|Authenticates Users| IdentityProvider
  SCIMServer1 -->|"Accesses External
Services"| ExternalService1
  SCIMServer2 -->|"Queries User
Data"| UserDirectory
  SCIMServer2 -->|Authenticates Users| IdentityProvider
  SCIMServer2 -->|"Accesses External
Services"| ExternalService2
  UserDirectory -->|User Data| Database

```



In this diagram:

- The "Clients" section represents external clients or applications (Client 1 and Client 2) that make SCIM requests.
- The "API Gateway" section represents the API Gateway, which serves as the entry point for SCIM requests and is responsible for load balancing requests.
- The "Load Balancer" section represents a load balancer that distributes incoming SCIM requests to multiple SCIM servers for scalability and redundancy.
- The "SCIM Server 1" and "SCIM Server 2" sections represent multiple SCIM servers handling SCIM operations.
- The "SAML 2.0 Identity Provider" section represents the SAML 2.0 Identity Provider used for user authentication.
- The "User Directory" section represents a user directory or database where user data is stored.
- The "External Services" section represents external services that the SCIM servers may interact with for various tasks.
- The "Database" section represents a database used for storing data related to SCIM operations.

