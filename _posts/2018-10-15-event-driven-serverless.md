---
layout: post
title:  "Event-Driven Serverless Architectures"
date:   2018-10-14 12:00:00 -0700
excerpt_separator: <!--more-->
---

Serverless - the latest and most 'cloud-native' approach to developing applications, offers increased agility, improved resilience and scalability, and a pure on-demand consumption-based cost model (though not without its trade-offs). However, to truly realize those benefits, we should look beyond the relatively narrow focus on Functions-as-a-Service (FaaS; or related variants such as BaaS (Backend), fPaaS (Function Platform), etc.). Basically, it is worthwhile to approach serverless from an architectural perspective; and more specifically, with event-driven serverless architectures.

![event-driven architecture](/assets/20181015-event-driven.png)
 <!--more-->

The focus on FaaS and the related considerations are still useful, as FaaS can be applied to a variety of use cases, especially when implemented as point solutions for a gradual decomposition of monolithic architectures into microservices, or simply sprinkle net-new microservices on existing systems to add new functionality (such as in a manner similar to the [Sidecar distributed computing pattern](https://docs.microsoft.com/en-us/azure/architecture/patterns/sidecar)). However, other than being able to run singularly focused units of work on an abstraction of immutable infrastructure, what truly differentiates serverless computing, is that it inherently advocates an event-driven architecture design. Thus, for this article we want to take a step further, and evaluate the design considerations when using serverless technologies for an entire application architecture. That is, to build a complete cloud-native application using event-driven serverless architectures.

## Architecture Design Principles

Now this isn't a brand new concept, as serverless computing builds upon microservices and domain-driven design, which builds upon service-oriented architectures (SOA) and [event-driven architecture]({{ site.baseurl }}{% post_url 2008-11-10-using-events-in-highly-distributed-architectures %}) (EDA), which build upon distributed computing best practices, etc. So a lot of the design fundamentals and best practices from the past still apply. Here we will just drill into ones that are relatively unique and/or interesting to serverless computing.

### Events over Functions
As we're alluding to, event-driven serverless architectures are, well, event-oriented. 😉 While synchronous request-response communication is still valid and useful, we should use 

Most SOA implementations are based on request/response communication, which introduces some
degree of direct coupling between the consumer and the service. Event-driven patterns support a
more decoupled form of communication. One component emits an event; one or more other
components listen for the event and take appropriate action. New components can be added to the
mix to perform additional functions without changing the existing components. This decoupling
enables services to change and scale independently of each other. In fact, pure microservice
implementation benefits from event-centric design as a core pattern, as it enables extremely loose
coupling and deployment flexibility.

Advice: Use event-driven communication models in combination with the ubiquitous request/
response. Report change of state ("something happened," such as an update of a bank balance) as
events, and pass commands ("do this," such as sending a notification) as requests to other
services. Set up infrastructure for mediating calls to both events and request APIs

Serverless functions are operated by function platforms as a service (fPaaS), also known as
functions as a service (or FaaS). Function platforms support the choice of event-driven and requestresponse
style invocation patterns. Choosing event-driven models can be more challenging early on
for unprepared application development teams, but the synergy of serverless functions and eventdriven
design is poised to deliver more advanced business outcomes.

### Meta over Data


### Functions over Services


### Choreography over Orchestration
monolithic large all-inclusive

### Composition over Integration
Clients over Services

## A Simple Example

![monolithic](/assets/20181015-monolithic-arch.png)

![serverless](/assets/20181015-event-driven-arch.png)


## Benefits and Challenges


