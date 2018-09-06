---
layout: post
title:  "Using Events in Highly Distributed Architectures (part 2)"
date:   2008-11-14 12:00:00 -0700
---

I had the privilege of publishing another article, "[Using Events in Highly Distributed Architectures](https://msdn.microsoft.com/en-us/library/dd129913.asp)", in the [Architecture Journal, issue 17](https://msdn.microsoft.com/en-us/library/dd129905.aspx), after the previous one on [Strong User Authentication on the Web](https://msdn.microsoft.com/en-us/cc838351.aspx) in issue 16.

![architecture journal](/assets/20081114-arcjournal.jpg)

Event-Driven Architecture (EDA) was discussed in this article, in terms of its concepts, and how it can be applied in enterprises as the next step of evolution in SOA initiatives.

The discussion took the direction of building on top of existing SOA infrastructures, so I didn't go into some key aspects for EDA, such as the importance of a robust and reliable messaging infrastructure that can ensure the reliable delivery of messages. It needs to support capabilities such as durable subscribers, message persistence and delivery tracking, idempotence, etc. Without a reliable messaging infrastructure, the collective architecture will not achieve a high level of data consistency, which is what EDA is ideally suited for.

I also did not go into much details, in the article, regarding modeling business processes as another logical layer on top of the asynchronous event distribution models. Now most practices today when modeling business processes follow very BPEL-like approaches - sequential logical workflows and orchestrations. And there are observations that many of these efforts, attempts to catalog or define enterprise business processes, often don't succeed at achieving the intended results. One possible explanation is that it is kind of "unnatural" to try to describe series of business activities as a sequentially linked list of tasks (with conditional branches, loops, etc.). Consequently, many architects end up not modeling the processes appropriately.

On the other hand, we can more easily map out business tasks as lifecycles or state transitions for each object, because that model is actually closer to how business analysts perceive business activities. The EDA perspective is that, in the context of asynchronous eventing models, these state transitions can then be defined into a state machine. Then, a layer of sequential workflows from a traditional business process definition perspective, can be added simply by drawing relationships across the state transitions of each object. It is a more abstracted view of business processes, but the underlying state machine model may bridge many of the gaps in traditional process modeling approaches, and can be mapped directly to an EDA technical implementation.

Lastly, asynchronous systems are inherently more scalable than synchronous systems. Today when people use asynchronous communication patterns to connect systems, they often integrate processes at a functional level (i.e., having logical dependencies on the outcomes of other distributed processes). As we move towards an environment where applications become much more inter-connected, both internally within an enterprise SOA environment, and with external partners via the open Internet (from a B2B perspective); and applications becoming more dependent on a growing number of externally distributed components, higher levels of functional decoupling will be needed to improve many aspects of the distributed architecture. EDA approaches seem to provide some relatively good answers from that perspective, but in practice, just like over-arching SOA initiatives, still have many challenges to overcome.

(originally published at <https://blogs.msdn.microsoft.com/dachou/2008/11/14/using-events-in-highly-distributed-architectures/>)