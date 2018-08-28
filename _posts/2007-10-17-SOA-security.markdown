---
layout: post
title:  "SOA Security – Enterprise Architecture Perspective"
date:   2007-10-17 10:18:22 -0700
categories: jekyll update
---
(originally published at [https://blogs.msdn.microsoft.com/dachou/2007/10/17/soa-security-enterprise-architecture-perspective/](https://blogs.msdn.microsoft.com/dachou/2007/10/17/soa-security-enterprise-architecture-perspective/))

This week I had the opportunity to speak at the IT Architect Regional Conference in San Diego, on the subject of architecting enterprise SOA security. It is an interesting event, with speakers from Microsoft, IBM, Oracle, TIBCO, Fair Issac, and many other organizations.

In a nutshell, my presentation was intended to point out the security aspects of planning an enterprise SOA, and a few topics that don't seem to be covered very often, and with an emphasis towards the future and navigating the organizational and cultural issues.

A brief overview -

![slide](/assets/20071017-soa-security-1.jpg)

Basically, some of the fundamental changes in SOA, such as:
- Moving from low-volume batch-oriented data replication architectures to highly interactive real-time architectures between connected systems 
- Plus the migration towards Event-Driven Architectures (EDA) means an exponential growth in real-time (though asynchronous) communication, as each event can potentially trigger off a number of downstream events which can trigger off more events being sent across the network 
- All this moves the security concerns from the traditionally isolated infrastructure and application groups, into the integration layer that becomes a cross-cutting concern for everyone involved 
- SOA can also magnify existing issues such as identity management (or the lack of), and create new issues such as exposing mainframes directly to web traffic (for sake of real-time access into legacy applications and data) 
- The ideal state of "everything talking to everything in real-time" also means a breakdown of traditional physical network zones/perimeters, where DMZ becomes more like a reception/lobby area instead of a quarantine area, and data centers can no longer be considered locked down 
- Lastly, the threat environment has also evolved from single PC attacks, to DoS system attacks, and to today's application and data-level attacks, with lowered complexity and lowered barrier of entry (facilitated by vastly improved competencies in using XML) 

Then of course, these changes also bring along many questions. Particularly many that represent conflicting approaches and each organization may come up with different solutions based on varying trade-offs.

![slide](/assets/20071017-soa-security-2.jpg)

For example,
- Trust vs. impersonation/delegation. There are many security groups that believe enterprise network environments are inherently unsafe (which is agreeable), and thus all systems will need to require end-user authentication (regardless whether they are user-facing or intermediaries or downstream producer systems), and that "trust" cannot be trusted 
- From a different perspective, this debate is also centered on the concept of implementing end-to-end vs. peer-to-peer security contexts 
- There is also a lot of recent discussion on moving security intelligence (w/ centralized management) into the endpoints (laptops, mobile devices, etc.), or moving intelligence into the network (like recent advances in NAC) 
In my opinion, trust-based architectures are much more flexible and scalable, and implementable by today's technology standards. And we couldn't completely eliminate trust in an impersonation/delegation model anyway. For example, a connected node/system has to "trust"  service wrappers, agents, and/or local system components to verify user credentials against a centralized repository (such as Active Directory, LDAP, etc.) anyway.

On the other hand, having end-to-end security contexts is indeed conceptually more secure, as it can help better address the man-in-the-middle attacks, but in an SOA with a number of intermediaries between consumers and producers, there is still not an effective solution in managing public keys to support end-to-end message-level data encryption.

![slide](/assets/20071017-soa-security-3.jpg)

It's always interesting to try to take a peek at what may be possible in the future.
- Most SOA discussions still seem to be focused on implementing "SOA in the enterprise". While that is very important, as enterprise architects we should also start to look at the growing trend of becoming more open on the Web, to an environment where enterprises essentially have no physical perimeters and security zones, largely due to the increasing number of direct and real-time connections into an enterprise (for sake of facilitating transactions with business partners). 
- Plus at that time we would also need to be concerned with the connections going from inside an enterprise out to the Web, as more and more internal systems becoming service consumers themselves 
- Thus a potential trend is moving away from trying to secure one large environment for the entire enterprise, migrating to a model where numerous (and potentially overlapping) smaller logical partitions (or zones) can be implemented to be provisioned with more targeted and effective security solutions (depending on data sensitivity). Rationale behind this is that it'll be more effective to try to protect smaller attack surfaces, even from a systems architecture perspective 
- Another interesting trend already underway is the growing centralization of data and content. Instead of consolidating everything into one or a few large enterprise content management deployments, organizations are creating smaller islands of data and content using collaboration platforms such as SharePoint. The point here is moving from mass distribution of data and content, and smaller islands seem to be lower hanging fruits at this point 

![slide](/assets/20071017-soa-security-4.jpg)

Finally, some overall talking points. One important and interesting point that was kind of new to many people is that security in SOA has to be planned and designed just like another process layer. If we overlook security and not plan it carefully, we may end up creating tightly coupled elements in the overall architecture, and impacting the agility we intended to create.

The most visible example of this is trying to implement message-level encryption for the sake of data integrity (message digests) and confidentiality. In order to establish an end-to-end security context (so that intermediaries, including the ESB, should not be able to decrypt sensitive data on transit to the destination), both the intended consumer and producer have to know exactly how to encrypt and decrypt data. And that depends on a previous exchange of public keys, which in this case had to occur directly between the consumer and producer endpoints. That in a way is tight coupling, as the consumer and producer endpoints have to know about each other, and are required to establish a one-to-one, peer-to-peer relationship in terms of public keys exchange used for encryption/decryption. To alleviate the situation, a centralized public key infrastructure can be implemented in an enterprise so that the management and decisions on public key usage can be externalized from endpoints and centralized. However, enterprise solutions in this area are still evolving, and we haven't yet seen effective solutions for doing similar things beyond the enterprise and on the Web.

Lastly, the most important point is that, just like SOA governance, security is also a huge factor of the organization and corporate culture. We have to take a process-first approach to the problem (instead of technology-first), then weave in the technology delivery part of it.

And here's the slide deck.
<iframe src="//www.slideshare.net/slideshow/embed_code/key/FlyadUv6mAvE3V" width="595" height="485" frameborder="0" marginwidth="0" marginheight="0" scrolling="no" style="border:1px solid #CCC; border-width:1px; margin-bottom:5px; max-width: 100%;" allowfullscreen> </iframe> <div style="margin-bottom:5px"> <strong> <a href="//www.slideshare.net/davidcchou/20071015-architecting-enterprise-security" title="20071015 Architecting Enterprise Security" target="_blank">20071015 Architecting Enterprise Security</a> </strong> from <strong><a href="https://www.slideshare.net/davidcchou" target="_blank">David Chou</a></strong> </div>

