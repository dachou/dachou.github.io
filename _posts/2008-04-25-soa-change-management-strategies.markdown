---
layout: post
title:  "SOA Change Management Strategies"
date:   2008-04-25 12:00:00 -0700
---
(originally published at [https://blogs.msdn.microsoft.com/dachou/2008/04/22/soa-change-management-strategies/](https://blogs.msdn.microsoft.com/dachou/2008/04/22/soa-change-management-strategies/))

By today's standards, it is pretty well-understood that governance is a critical success factor for enterprise SOA initiatives. And there is already a considerably saturated/consolidated market providing the SOA governance solutions (see Gartner's [Magic Quadrant for Integrated SOA Governance Technology Sets, 2007](http://mediaproducts.gartner.com/reprints/hp/vol1/article4/article4.html), Forrestor's [SOA Service Life-Cycle Management Q1 2008](http://www.softwareag.com/Corporate/Images/The%20Forrester%20Wave-SOA%20Service%20Life-Cycle%20Management,%20Q1%202008_tcm16-38231.pdf), and [SOA Governance Conference 5](http://www.soagovcon5.com/) for some content from HP, IBM, Progress Software, and SOA Software).
 
A quick glance over the product features and discussions finds that the SOA governance tools in the market today focus on a set of key capabilities:

- Design-time lifecycle management (contracts & metadata & artifacts management, change & reporting notification plus automation, QA and test automation, dependencies mapping, policy compliance auditing, etc.) 
- Run-time lifecycle management (versioning, decommissioning, monitoring & reporting, change deployment management, usage and exceptions metrics collection, policy compliance enforcement, etc.) 
- Security and access control (policy-driven fine-grained service authorization) 
- Integration with service infrastructure (ESB, identity management, single sign-on, MDM, service registries, metadata repositories, PKI, etc.) 

Just one way of categorizing the capabilities. Most vendors have their own ways of categorizing/describing these products, and some provide more built-in features. These capabilities are quite advanced and do address a wide range of governance needs. And then there is another set of products that aims to address SOA testing and automation needs.

**How to Validate Incremental Changes Deployed to a Live, Real-Time, Inter-Connected, and Inter-Dependent Distributed Architecture?**

The SOA governance tools support this from the perspective of making sure services are developed in compliance to policies and defined contracts, then managed in runtime after deployment and release. The SOA testing tools support this from managing and automating test efforts against component-based service deployments. However, there seems to be a considerable gap in terms of validating and managing changes in an enterprise SOA environment.

A closer look uncovers many tough questions:

- How do we validate changes in an SOA where a set of (sometimes hundreds of) physically distributed systems and services have been managed and governed into one logical/virtual entity? Specifically, how do we ensure a particular change being released into the live production environment won't break anything else, which often are other connected mission-critical systems that are running concurrently, based on traditional multi-staging change management strategies? 
- Do we trust that changes verified in a QA environment will behave exactly the same in production? If so, is the QA environment an exact replica of production, including the operational data that processing logic depends on? 
- Do we just "unit test" the service components associated with a unit of change, or do we work with other teams to conduct a full integration test in QA? And in an integration test, is the whole virtual enterprise involved, or just the directly connected system components? 
- How do we ensure that downstream components connected in multi-part, distributed transactions are not impacted if we don't conduct integration tests on everything? 
- How do we ensure that the QA environment is pristine and how do we coordinate among multiple team's project schedules, which are often more different than similar? 
- In a highly inter-connected and inter-dependent environment, how do we manage the worst-case scenario where hundreds of service components are impacted by a change? 
- If change verification/testing in production is allowed, how do we facilitate synthetic transactions so that actual production data is not interfered by test cases? 

**SOA Requires Different Methods of Managing Changes**

Well that's obvious, right? 🙂 But fundamentally it probably requires a different way of thinking too. For example, traditional multi-staging change migration strategies (dev, test, QA, staging/regression, prod, etc.) don't lend themselves very well anymore as they were more effective at managing changes that are more autonomous and local in nature. Now that changes are inter-related and inter-dependent, and often impacting a high number of systems not under any one team's management, full integration tests may mean coordinating schedules, code/data versions, security, etc. all bundled into one massive enterprise-wide test. Which would be too difficult and complex to undertake on a regular basis, and as a result what happens to the agility SOA was intended to deliver?

The SOA governance tools today address this change management need mainly via service lifecycle management, so that newer versions of services can be deployed with minimal initial dependencies. Then over time consumers can be migrated over from the older versions in their own independent schedules, and eventually the older versions can be decommissioned once no one is using them anymore. However, it isn't always that applications can support multiple versions of the same service (and best practices on when a new version is required as opposed to hot fixes is still unclear), or the trade-offs in management costs may not justify doing so.

And is the only effective solution to manage changes in an SOA environment, to implement SOA governance tools? Tools are tools, and they do help, but often they also bring a layer of complexity as well. And governance tools are best suited to support specific processes defined in specific architectures; they don't actually solve problems in this area, as the problems are due to the collective processes and systems bound together in an SOA. Thus, well-defined processes and architectures are still required, then tools can be used for automation and enforcement.

**Build Layers of Encapsulation and Abstraction Into an SOA**

This concept is markedly different from the initial intention of transforming a disconnected and silo'ed enterprise into one seamless entity. But basically, one massive logical SOA may actually be more difficult to manage, than a set of smaller localized/partitioned SOA's federating as one. Even though more costly from an infrastructure perspective, there are many benefits to this approach (especially for larger enterprise environments):

- Layers of abstraction/encapsulation provide boundaries where changes can be localized instead of being required to be verified against the entire end-to-end architecture 
- Allows for shrinking and localizing the scope of impacted components in integration tests, into smaller and more discrete units which become easier to coordinate and schedule between smaller number of involved teams 
- Still not effective at addressing changes that impact a high number of systems, but smaller and localized changes no longer have to be tied up and wait for the "big test" to complete, to be released 
- Over time, the entire architecture is re-validated 
- From a security perspective, this supports defense in depth 

ESB vendors will like this, as these products are the most effective solutions to build in layers of encapsulation/abstraction into an SOA. But there are many different kinds of ESB's in the market. Point is, from an enterprise architecture perspective, we really don't need to migrate to a full centralization model when implementing an SOA. A model where local SOA's federate into one enterprise SOA may work out better, providing sufficient local autonomy (type of ESB, local governance, etc.) while coherently organizes the enterprise into one logical entity, and likely higher scalability, reliability, and agility.

Also, data integration/replication, even though often cited as a major anti-pattern in SOA, when applied appropriately, is often an effective way to add a layer between different systems, when an encapsulation layer is preferred. Basically, inter-dependencies are minimized if there are no distributed transactions binding systems together at the process level.

**A Different Process-Oriented Approach**

A resulting SOA validation strategy is to have a centralized management of integration testing schedule in the enterprise QA environment, so that at any one point in time, only one set of changes is being validated. As a result, most integration tests should occur in localized groups and at more discrete intervals/schedules, as opposed to trying to get everyone to undergo validation at the same time, or cause people to run over each other with conflicting changes.

Thus there are three testing models: unit test, localized integration test, and full integration test. Full integration tests are usually preferred (perceived to be more accurate and comprehensive), but also too cost-prohibitive to undertake. The best trade-off is localized integration tests performed at more discrete and distributed schedules, as each validation can assume it’s done in a pristine environment, and logically the entire architecture is re-validated over time.

In addition, from a SLA or security management perspective, systems are often categorized into different criticality tiers. In an ideal SOA where everything is connected to everything, it shouldn’t mean that everything is now molded into the same tier. Consequently, different strategies can be devised to re-validate systems in different tiers. For example, only require unit test for systems in lower tiers.

The enterprise perspective can be that, all three types of tests are done; it’s just management effort that is required. For example, a full integration test can be scheduled on a quarterly basis, while localized integration tests are used to release regular changes.

**SOA Change Management Requires a Multi-Faceted Approach**

There are still some areas where the current set of SOA governance and testing tools don't address very well. It's not that these products lack maturity; it's just some issues are inherent in distributed computing and are created by the collection of design decisions, processes and methodologies, and technologies implemented in an SOA (which obviously, can be different for each organization). The SOA governance solution vendors themselves state that governance is a people-oriented process.

Thus, when architecting SOA governance, additional thought needs to be placed in these areas, in a change management context, and integrated into many different aspects of an SOA, leveraging an integrated approach across people, processes, and technologies.