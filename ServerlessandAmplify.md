# Serverless and Amplify

Serverless is a cloud computing execution model where the cloud provider 
dynamically manages the allocation and provision of servers.
A serverless application runs in stateless compute containers 
that are event-triggered, ephemeral, and fully managed by the cloud provider. 

for a long, the traditional architecture was to run the server for the application and deal with its problems all the time but with serverless,
you no longer need to worry about the underlying servers. The reason is, that they are not managed by you anymore, and with management out of the picture the responsibility falls on the Cloud vendors

- pricing

  pricing is one of the major advantages of using serverless because you don't pay for computing capacity but for the number of execution per second  
- Networking

  Serverless functions are accessed only as private APIs. To access these you must set up an API Gateway. This doesn’t  impact pricing or process, but it means you cannot directly access them through the usual IP

## Functions as a Service
Function-as-a-Service, or FaaS, is a kind of cloud computing service that allows developers to build, compute, run, and manage application packages as functions without having to maintain their own infrastructure.

FaaS is an event-driven execution model that runs in stateless containers and those functions manage server-side logic and state through the use of services from a FaaS provider.

### Principles of FaaS:
- Complete management of servers
- Invocation based billing
- Event-driven and instantaneously scalable


## Benefits of Serverless Architecture
- The cost incurred by a serverless application is based on the number of function executions, measured in milliseconds instead of hours.
- Process agility: Smaller deployable units result in faster delivery of features to the market, increasing the ability to adapt to change.
- Cost of hiring backend infrastructure engineers goes down.
- Reduced operational costs

for developer 
-Scalable, no need to worry about the number of concurrent requests.
- Reduced liability, no backend infrastructure to be responsible for.

## Drawbacks of Serverless Architecture
- Reduced overall control.
- Vendor lock-in requires more trust for a third-party provider.
- Additional exposure to risk requires more trust for a third-party provider.
- Security risk.

for developer
- Immature technology results in component fragmentation, unclear best-practices.
- Architectural complexity.
- Execution duration is capped.


resources

[What is Serverless Architecture? What are its Pros and Cons?](https://hackernoon.com/what-is-serverless-architecture-what-are-its-pros-and-cons-cc4b804022e9)
