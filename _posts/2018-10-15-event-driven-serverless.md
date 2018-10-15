---
layout: post
title:  "Event-Driven Serverless Architectures"
date:   2018-10-16 12:00:00 -0700
excerpt_separator: <!--more-->
---

Serverless - the latest and most 'cloud-native' approach to developing applications, offers increased agility, improved resilience and scalability, and a pure on-demand consumption-based cost model (though not without its trade-offs). However, to truly realize those benefits and to deliver more advanced outcomes, we should look beyond the relatively narrow focus on Functions-as-a-Service (FaaS; or related variants such as BaaS (Backend), fPaaS (Function Platform), etc.). Basically, it is worthwhile to approach serverless from an architectural perspective; and more specifically, with event-driven serverless architectures.

![event-driven architecture](/assets/20181015-event-driven.png)
 <!--more-->

The focus on FaaS and the related considerations are still useful, as FaaS can be applied to a variety of use cases, especially when implemented as point solutions for a gradual decomposition of monolithic architectures into microservices, or simply sprinkle net-new microservices on existing systems to add new functionality (such as in a manner similar to the [Sidecar distributed computing pattern](https://docs.microsoft.com/en-us/azure/architecture/patterns/sidecar)). However, other than being able to run singularly focused units of work on an abstraction of immutable infrastructure, what truly differentiates serverless computing, is that it inherently advocates an event-driven architecture design. Thus, for this article we want to take a step further, and evaluate the design considerations when using serverless technologies for an entire application architecture. That is, to build a complete cloud-native application using event-driven serverless architectures.

## Architecture Design Principles

Now this isn't a brand new concept, as serverless computing builds upon microservices and domain-driven design, which builds upon service-oriented architectures (SOA) and [event-driven architecture]({{ site.baseurl }}{% post_url 2008-11-10-using-events-in-highly-distributed-architectures %}) (EDA), which build upon distributed computing best practices, etc. So a lot of the design fundamentals and best practices from the past still apply. Here are some that have some unique elements and/or especially interesting to serverless computing.
- Events over Functions
- Microservices over Monoliths
- Meta over Data
- Distributed over Stateless
- Consumer over Service
- Choreography over Orchestration
- Composition over Integration

More elaboration on these below.

### Events over Functions
As we're alluding to, event-driven serverless architectures are, well, event-oriented. 😉 Even though function platforms support both event-driven and request/response service invocation patterns, we should use use an event-driven design as the default communication model.

Event-driven design inherently enables loose coupling, which enables service abstraction and isolation, deployment flexibility, independent scale, etc. This is especially relevant to function platforms because functions are inherently fine-grained, and a loosely coupled architecture enables the functions/services to operate independently similar to individual musicians in a symphonic orchestra.

That is, loose coupling is key to enabling more smaller components to work effectively together, while leveraging their operational independence, auto-scaling, and on-demand cost models; as opposed to fewer larger components. 

![lego](/assets/20100930-lego.png)

Or, one more analogy with LEGO bricks - we can easily see how the regular LEGO bricks (~4,000 parts) are more flexible and scalable (in terms of the things we can build), than the fewer and larger Duplo bricks. Similarly with serverless computing - we get more agility from a loosely coupled system made up of many fine-grained services. This is consistent with 

Thus from a design perspective, taking an events-first approach helps to drive towards an event-driven architecture, which leads into many of the principles below. This means thinking about organizing application logic as reactive elements to events, where events can represent a change in state (e.g., something happened), or a task submission (e.g., do something). This then leads into functional design, which is a different sequence than when a functions-first approach is used. The end result is a more loosely coupled architecture that looks like a set of discrete microservices operating indepdently, working directly with a number of resources (e.g., database, storage, service API's, etc.), and tied together by events that don't necessarily map to sequential workflows.

This type of architecture design is especially effective at supporting modern applications with unpredictable scale and user demand. Event-driven design helps with concurrency as it breaks down large sequential transactions into a number of smaller parallel tasks. Serverless functions help with the operational aspects of auto-scaling and resiliency of individual processes to fulfill these tasks, without the development teams to be concerned with provisioning the necessary infrastructure to manage spikes in demand, and to handle concurrency, while maintaining cost levels accordingly.

### Microservices over Monoliths

This isn't a general statement against monolithic applications, as monoliths are an effective approach for some application scenarios, just as serverless computing isn't suitable for all application scenarios. However, serverless platform implementations inherently follow the microservices model, thus a microservices design is favored over monolithic design.

Of course, we can still deploy monoliths into function platforms; just letting the platform invoke an entry point into the monolithic application. However, most function platforms have constraints such as execution duration, memory allocation size, etc. which is likely insufficient for large monoliths. So for serverless computing, systems composed of small, independent, and interconnected units of functionality, are favored over larger bundles of functionality.

Thus, many of the existing best practices in designing microservices apply in serverless computing as well. However, there are some differentiating aspects, such as the concept of decentralized data management, which microservices architectures advocate each 'service' to own and encapsulate its database and dependent services, and that other services in a system should not create 'back doors' to access those 'internal' resources directly.

In event-driven serverless architectures, this could be slightly different as we can further decompose a 'service' down to multiple 'functions', where a set of functions may need to manage the same set of data. And to maintain a consistent level of serverless-ness, an architecture should use a common data management solution that aligns with serverless computing requirements (e.g., Azure Cosmos DB). In this case, it may be more effective to use a modular and/or sharded data design approach (e.g., decomposing the database down to smaller Collections and keeping certain data Collections mapped to a set of functions as an aggregate) instead of enforcing separate physical databases. And perhaps implement a quasi-CQRS model where all writes go through a specific function, but reads can be queried directly (via platform bindings) against the database; as long as an eventual consistency model is acceptable, since Azure Cosmos DB and highly distributed architectures like serverless advocate eventual consistency.

Thus, even though serverless computing favors a microservices design, we still need to carefully consider the granularity of individual functions and how data is managed; weighing trade-offs in service autonomy, change and service versioning management, scale and concurrency, value of agility, etc.

### Meta over Data

Event-driven serverless architectures advocate passing metadata instead of actual data, between units of tasks (functions). This is especially relevant as direct cross-function communication is discouraged, and in those scenarios a message queue should instead be used to maintain loose coupling at a system level. However, most message queue solutions also have a limit in message sizes.

From the perspective of events, metadata consists of information that describes 'something happened' in the system, specific information relevant to the event, and common logistical elements such as event source, timestamp, and unique identifier.

For example, the storage system publishes an event that a file has been uploaded by a user. The event message itself would only contain the event type (e.g., "file uploaded"), and path/url information to the file. The consumer function of this event can decide what to do with the information, such as to download the file from the storage system and do its work (such as resizing the image into a fixed size and sending it to a computer vision service to recognize its contents) and then write data resulting from the work into the database, related to the user's account. The user's account lookup required this function to extract the internalized identifier from the path/url (container assigned to the user) and query the database to access the account informaiton.

Hence the related thought earlier regarding distributed data management in microservices design. Since direct, synchronous request/response between functions is not encouraged, we shouldn't create atomic data 'read' functions to be invoked by functions that need to lookup data, but writes should be submitted to a function to 'do the work'. This means building on an eventual consistency model provided by a serverless database solution (such as Azure Cosmos DB), and use the platform bindings to execute read queries directly from the database.

Metadata from this perspective should be immutable and not dependent on application state. Instead, user and application state should be maintained in a database solution that ensures data integrity and consistency, so no state is maintained in the form of events that live outside of the serverless database.

### Distributed over Stateless

While functions should be written to be stateless (shared nothing) and idempotent (consistently same output from same input), the composite system (end-to-end architecture) in most cases does maintain application state in some form. The distinction is that, processes (functions) should be stateless, similar to events (that carry only metadata), so that any state is only maintained by stateful resources.

These resources can be serverless databases, distributed storage, message queue solutions, and other service API's (that are implemented by their own architectures with data and dependencies encapsulated). From this perspective, application state is distributed among a set of resources in a system, and not stored and managed in a centralized resource. These platform resources themselves should operate in a model that align with event-driven serverless architectures (or microservices), with a consistent level of independent resiliency and scalability.

For example, Azure Cosmos DB may be the primary serverless database resource in Azure, but instead of thinking of it as one centralized database, application state should be decomposed into separate collections mapped to relevant sets of functions, or use sharding for larger data sets. Basically, follow the microservices best practices in domain-driven design, where a function/data aggregate works with its own domain model within a bounded context (and use of canonical models is discouraged to minimize contention). Then there could also be files in Blob Storage, vertically aligned data in Table Storage, transient data in Redis Cache, etc. And when possible, push user session state to the client, such as in the cases of mobile apps, rich HTML/JS client apps (e.g., Single Page Apps).

As a result, application state is distributed across the platform resources an architecture employs. From a design perspective, following a distributed state approach (system-oriented as opposed to focus on 'stateless') and leverage the resources to do their work, enables functions to be stateless (as a result), and reach a consistent level of serverless-ness in the composite system architecture.

### Consumer over Service

An event-driven model enables us to take a more consumer-centric approach to designing API's for services (as opposed to service-centric). And specifically for event-driven serverless architectures, is is more effective to approach the designs of events and interactions between functions and resources from a consumer (or user, client, publisher) perspective.

Traditionally, the design of a system tends to be driven from the back-end; by first defining the data models, then application processes to manage the data, then service interface definitions to expose functionality to consumers. The consumer of these services then is responsible for understanding the service domain, the semantics of the service API's, and often needs to grapple with a client SDK (which is needed to simplify interactions with the service API's), etc. As a result, the application design is service-centric, in that the onus is on the consumer to conform to the requirements of the services.

Taking a functions-led approach also tends to drive the design from the backend (service-centric). However, because of the loose coupling enabled in an event-driven model, we can drive the design from the frontend; using a consumer-centric (or user, client, publisher) perspective. This is because in an event-driven model, the event publisher (traditionally client/consumer role) drives the definition of the event, then it simply submits the event into an eventing system (or queue infrastructure), without any knowledge of the implementation details of the subscriber (traditionally service role). The onus is then on the subscriber (service) to adapt to the event and do its work.

Of course, technically we can still have the service implementation to define how an event message needs to look like (e.g., an exact JSON document format) that event publishers need to adhere to. But if we take a consumer-oriented approach, and leverage the function platform's built-in capabilities such as agile code deployments, versioning, proxies, API mediation, etc., we would end up having a more flexible system that is more agile and adaptable to business and technical changes.

### Choreography over Orchestration

The design of workflows or logical processes in an event-driven architecture should land in a choreography model, as opposed to an orchestration model.

An orchestration model points to a centralized process-driven view of sequential workflow, mostly aligned with synchronous request/response process that tightly manages the end-to-end execution of logic and interaction with resources to complete a transaction. A choreography model points to independent services that work in tandem and reacting to events separately (or in parallel) to accomplish a logical task. The subtle difference is that orchestration is a process-centric view, vs. choregraphy is a resources and functions-oriented view.

Basically, this highlights the thought to resist the urge to design workflows as traditional sequential (or in a way, monolithic) process in a service implementation. Rather, approach the design from the use of resources needed for a task, then logic in functions to interact with the resources, and invoked via events. Consequently, a logical transaction in an event-driven architecture may result in the execution of multiple parallel tasks activated by events that represent changes in resources. These tasks have no knowledge of each other's execution and implementation details, but the collective result of their work accomplishes the intended output of a user/system transaction.

### Composition over Integration



## A Simple Example

![monolithic](/assets/20181015-monolithic-arch.png)

![serverless](/assets/20181015-event-driven-arch.png)


## Benefits and Challenges

experimentation, versioning
bundle tasks around aggregates boundaries, consistent data together
arbitrage over different charging models
file upload to server using cycles
request-level authorization
