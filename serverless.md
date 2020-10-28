# SERVERLESS  
[Home](./README.md) 

[Overview](https://hackernoon.com/what-is-serverless-architecture-what-are-its-pros-and-cons-cc4b804022e9)  

__WHY?__:
 * It promises the possibility of ideal business implementations which sounds quite pleasant to the ears and probably light on the budget as well.  
 * Serverless is a cloud computing execution model where the cloud provider dynamically manages the allocation and provisioning of servers. 
 * A serverless application runs in stateless compute containers that are event-triggered, ephemeral (may last for one invocation), and fully managed by the cloud provider. Pricing is based on the number of executions rather than pre-purchased compute capacity

 __Pros:__
 1. Pricing (priced on memory and number of executions)
 2. Environments
 3. Scalability

 __Cons:__
 1. Networking (needs private API)
 2. 3rd party dependencies  
 3. Timeout (With Serverless computing, there’s a hard 300-second timeout limit. Too complex or long-running functions aren’t good for Serverless)  
 4. Scalability( Scaling process for Serverless is automatic and seamless, but there is a lack of control or entire absence of control.)


__Function as a service(FaaS):__
![overview](https://hackernoon.com/hn-images/1*TIrjN7EjLUVJmJ6YvHR7Dg.png)