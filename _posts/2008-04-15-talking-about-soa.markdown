---
layout: post
title:  "Talking about Service Oriented Architecture"
date:   2008-04-15 10:00:00 -0700
---

I had the privilege to speak at the April monthly meeting at the Los Angeles Java Users Group. The meeting was held on April 1st at the Sun Microsystems office in LA, and so that in itself was the source of a few jokes lobbed at me. At times I was also referred to as Darth Vader (since I used to work at Sun and now I'm at Microsoft), but all in good fun. 

It was a great time chatting with the group, and was fortunate enough to see some familiar faces, especially a few back in the days when I worked at Sun Microsystems at this same office.
The topic of my presentation was "Service Oriented Architecture". This was picked as SOA is something that can be talked about from a technology-agnostic perspective, especially if we're focusing on the "A" in SOA.

The presentation was mostly repeating what is considered "common knowledge" in SOA these days, such that SOA is an "architectural style", and that most of the fundamental principles consist of best practices and learned lessons in software and systems engineering in distributed computing, in the IT industry; and applied towards enterprise IT and systems integration efforts. And SOA is a pretty overloaded term too, such that many different perspectives exist, but all are valid:

Organizationally - developers, architects, managers, business stakeholders, executives, etc.

Architecturally - enterprise, infrastructure, security, data, integration, application, etc.

But in general, there is no one form of SOA that fits all organizations. Large enterprises tend to have a different set of issues and solution approaches at different priorities compared to medium-to-small businesses. The kind of SOA implemented at one organization may not necessarily be effective or needed for another organization. Just the same as all problem-solving scenarios, it is most effective to fully understand the issues, and then figure out approaches to address them.

Similarly, a maturity model-based approach is an excellent way to plan an SOA journey, but no existing maturity model (available from most of the technology vendors and analysts) is necessarily the right one to use. It's more important to pick out the aspects in a few maturity models that work for each organization, than to try to follow/implement a specific one religiously.

Meanwhile, many organizations looking at SOA are also faced with a number of questions at the implementation level:

- Process vs. data integration
- SOAP vs. REST
- Data federation vs. data replication
- Synchronous (RPC) vs. asynchronous (EDA)
- Transactional (2PC / compensational) or not
- Trust vs. impersonation
- Centralized vs. federated ESB (or no ESB at all)
- Stateful (BPM) vs. stateless (orchestrations)
- Real-time vs. latencies

Conceptually, transforming a traditionally silo'ed enterprise environment into one logical real-time entity does seem to be a really beneficial proposition. However, that is often very difficult to obtain. Some of the factors include transforming all systems to be 24/7 instead of having independent maintenance outage windows, bear the transaction volumes of the highest trafficked systems, coordinating integration tests between multiple teams (or the entire enterprise), be subjected to the highest security compliance, etc.; when many didn't have to be when they were back in the silo environments.

Lastly, what may SOA look like in the future? There's talk about event-driven architecture (EDA) as the next step in evolution, which could be a more natural way of integrating business processes than the current RPC-style of tying everything together. There is also talk about extending SOA out to the Web, for enterprises, and additional advances in cloud computing, such as infrastructure services like internet service bus(es), federated security, cloud-based identity management and privacy controls, cloud-based data transformation services, etc. Continued progress in the semantic and interpretive Web may also play a major role in adding context to Web as a platform. And advances in model-driven programming and integrating them into service-oriented compositional architectures (such as Oslo on the Microsoft side, and SCA on the Java side) that change traditional multi-tiered application architectures to fully composite application architectures in all tiers (client-side mash-ups plus server-side mash-ups).

<iframe src="//www.slideshare.net/slideshow/embed_code/key/7WWeQnsyjWWjVL" width="595" height="485" frameborder="0" marginwidth="0" marginheight="0" scrolling="no" style="border:1px solid #CCC; border-width:1px; margin-bottom:5px; max-width: 100%;" allowfullscreen> </iframe> <div style="margin-bottom:5px"> <strong> <a href="//www.slideshare.net/davidcchou/soa-today-and-beyond" title="20080401 SOA - Today and Beyond" target="_blank">20080401 SOA - Today and Beyond</a> </strong> from <strong><a href="https://www.slideshare.net/davidcchou" target="_blank">David Chou</a></strong> </div>

(originally published at <https://blogs.msdn.microsoft.com/dachou/2008/04/15/talking-about-service-oriented-architecture/>)
