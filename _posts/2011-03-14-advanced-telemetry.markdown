---
layout: post
title:  "Cloud-optimized architecture and Advanced Telemetry"
date:   2011-03-14 12:00:00 -0700
---

![advanced telemetry](/assets/20110314-advancedtelemetry.jpg)

One of the projects I had the privilege of working with this past year, is the Windows Azure platform implementation at Advanced Telemetry. Advanced Telemetry offers an extensible, remote, energy-monitoring-and-control software framework suitable for a number of use case scenarios. One of their current product offerings is EcoView™, a smart energy and resource management system for both residential and small commercial applications. Cloud-based and entirely Web accessible, EcoView enables customers to view, manage, and reduce their resource consumption (and thus utility bills and carbon footprint), all in real-time via the intelligent on-site control panel and remotely via the Internet.

![architecture](/assets/20110314_05B1BC70.png)

Much more than Internet-enabled thermostats and device end-points, “[a tremendous amount of work has gone into the core platform, internally known as the TAF (Telemetry Application Framework) over the past 7 years](http://at-cto.blogspot.com/2010/10/power-of-platform.html)” (as Tom Naylor, CEO/CTO of Advanced Telemetry wrote on his blog), which makes up the server-side middleware system implementation, and provides the intelligence to the network of control panels (with EcoView being one of the applications), and an interesting potential [third-party application model](http://at-cto.blogspot.com/2010/07/apps-apps-everywhere-apps.html).

The focus of the Windows Azure platform implementation, was moving the previously hosted server-based architecture into the cloud. Advanced Telemetry completed the migration in 2010, and the Telemetry Application Framework is now running in Windows Azure Platform. Tom shared some insight from the experience in his blog post “[Launching Into the Cloud](http://at-cto.blogspot.com/2010/04/launching-into-cloud.html)”. And of course, this effort was also highlighted as a Microsoft case study on multiple occasions:
- [Energy Monitoring Firm Saves Money, Scales Business with Hosted Computing Platform](http://www.microsoft.com/casestudies/Case_Study_Detail.aspx?CaseStudyID=4000005893) 
- [Startup Uses Cloud Computing to Change Business Model, Becomes Instantly Profitable](http://www.microsoft.com/casestudies/Case_Study_Detail.aspx?CaseStudyID=4000009076) 
- SQL Azure team blog’s [Interview with Tom Naylor, CTO of Advanced Telemetry](http://blogs.msdn.com/b/sqlazure/archive/2011/01/24/10119498.aspx) 
- Windows Azure AppFabric team blog’s [How Advanced Telemetry became instantly profitable after migrating to the Windows Azure Platform](http://blogs.msdn.com/b/windowsazureappfabric/archive/2011/01/25/how-advanced-telemetry-became-instantly-profitable-after-migrating-to-the-windows-azure-platform.aspx)
- Channel 9 Video - [Building on Azure: Advanced Telemetry](https://channel9.msdn.com/Shows/Inside+Out/Building-on-Azure-Advanced-Telemetry) 
 
## The Move to the Cloud

As pointed out by the first case study, the initial motivation to adopt cloud computing was driven by the need to reduce operational costs of maintaining an IT infrastructure, while being able to scale the business forward.

> “We see the Windows Azure platform as an alternative to both managing and supporting collocated servers and having support personnel on our side dedicated to making sure the system is always up and the application is always running,” says Tom Naylor. “Windows Azure solves all those things for us effectively with the redundancy and fault tolerance we need. Because cost is based on usage, we’ll also be able to much more accurately assess our service fees. For the first time, we’ll be able to tell exactly how much it costs to service a particular site.”

For instance, in the Channel 9 video, Tom mentioned that replicating the co-located architecture from Rackspace to Windows Azure platform resulted in approximately 75% cost reduction on a monthly basis in addition to other benefits. One of the major ‘other’ benefits is agility, which arguably is much more valuable than the cost reduction normally associated with cloud computing benefits. In fact, as the second case study pointed out, in addition to breaking ties to an IT infrastructure, Windows Azure platform become a change enabler that supported to shift to a completely different business model for Advanced Telemetry (from a direct market approach to that of an original equipment manufacturer (OEM) model). The move to Windows Azure platform provided the much needed scalability (of the technical infrastructure), flexibility (to adapt to additional vertical market scenarios), and manageability (maintaining the level of administrative efforts while growing the business operations). The general benefits cited in the case study were:
- Opens New Markets with OEM Business Model
- Reduces Operational Costs
- Gains New Revenue Stream
- Improves Customer Service

## Cloud-Optimized Architecture

However, this is not just another simple story of migrating software from one data center to another data center. Tom Naylor understood well the principles of cloud computing, and saw the value in optimizing the implementation for the cloud platform instead of just using it as a hosting environment for the same thing from somewhere else. I discussed this in more detail in a previous post [Designing for Cloud-Optimized Architecture]({{ site.baseurl }}{% post_url 2011-01-23-designing-for-cloud-optimized-architecture %}). Basically, it is about leveraging cloud computing as a way of computing and as a new development paradigm. Sure, conventional hosting scenarios do work in cloud computing, but there is more value and benefits to gain if an application is designed and optimized specifically to operate in the cloud, and built using unique features from the underlying cloud platform.

In addition to the design principles around “small pieces, loosely coupled” fundamental concept I discussed previously, another aspect of the cloud-optimized approach is to think about storage first, as opposed to thinking about compute. This is because, in cloud platforms like Windows Azure platform, we can build applications using the cloud-based storage services such as Windows Azure Blob Storage and Windows Azure Table Storage, which are horizontally scalable distributed storage systems that can store petabytes and petabytes of data and content without requiring us to implement and manage the infrastructure. This is in fact, one of the significant differences between cloud platforms and traditional outsourced hosting providers.

In the Channel 9 video interview, Tom Naylor said “what really drove us to it, honestly, was storage”. He mentioned that the Telemetry Application Platform currently handles about 200,000 messages per hour, each containing up to 10 individual point updates (which roughly equates to 500 updates per second). While this level of traffic volume isn’t comparable to the top websites in the world, it still poses significant issues for a startup company to store and access the data effectively. In fact, the data required the Advanced Telemetry team to cull the data periodically in order to maintain a relatively workable size for the operational data.

> “We simply broke down the functional components, interfaces and services and began replicating them while taking full advantage of the new technologies available in Azure such as table storage, BLOB storage, queues, service bus and worker roles. This turned out to be a very liberating experience and although we had already identified the basic design and architecture as part of the previous migration plan, we ended up making some key changes once unencumbered from the constraints inherent in the transitional strategy. The net result is that in approximately 6 weeks, with only 2 team members dedicated to it (yours truly included), we ended up fully replicating our existing system as a 100% Azure application. We were still able to reuse a large percentage of our existing code base and ended up keeping many of the database-driven functions encapsulated in stored procedures and triggers by leveraging SQL Azure.” Tom Naylor described the approach on his blog.

The application architecture employed many cloud-optimized designs, such as:
- Hybrid relational and noSQL data storage – SQL Azure for data that is inherently relational, and Windows Azure Table Storage for historical data and events, etc.
- Event-driven design – Web roles receiving messages act as event capture layer, but asynchronously off-loads processing to Worker roles

## Lessons Learned
In the real world, things rarely go completely as anticipated/planned. And it was the case for this real-world implementation as well. 🙂 Tom Naylor was very candid about some of the challenges he encountered:
- Early adopter challenges and learning new technologies – Windows Azure Table and Blob Storage, and Windows Azure AppFabric Service Bus are new technologies and have very different constructs and interaction methods
- “The way you insert and access the data is fairly unique compared to traditional relational data access”, said Tom, such as the use of “row keys, combined row keys in table storage and using those in queries”
- Transactions - initial design was very asynchronous; store in Windows Azure Blob storage and put in Windows Azure Queue, but that  resulted in a lot of transactions and significant costs based on the per-transaction charge model for Windows Azure Queue. Had to leverage Windows Azure AppFabric Service Bus to reduce that impact

The end result is a an application that is horizontally scalable, allowing Advanced Telemetry to elastically scale up or down the deployments of individual layers according to capacity needs, as different application layers are nicely decoupled from each other, and the application is decoupled from horizontally scalable storage. Moreover, the cloud-optimized architecture supports both multi-tenant and single-tenant deployment models, enabling Advanced Telemetry to support customers who have higher data isolation requirements.

(originally published at <https://blogs.msdn.microsoft.com/dachou/2011/03/14/cloud-optimized-architecture-and-advanced-telemetry/>)
