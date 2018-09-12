---
layout: post
title:  "SOA – End of Life 2009.01.01"
date:   2009-01-09 12:00:00 -0700
---

It has just been a few days since Anne Thomas Manes at Burton Group published her post “[SOA is Dead; Long Live Services](http://apsblog.burtongroup.com/2009/01/soa-is-dead-long-live-services.html)”, and it has stirred up quite a storm of comments in the blogosphere. Most of what I read though, seem to be in alignment with what Anne Thomas Manes said -

> SOA met its demise on January 1, 2009, when it was wiped out by the catastrophic impact of the economic recession. SOA is survived by its offspring: mashups, BPM, SaaS, Cloud Computing, and all other architectural approaches that depend on “services”.

Her article clarified that it is the “SOA as we know” (and the terminology used) has faded into irrelevance, the SOA that called for a comprehensive transformation of an organization’s view and management of its portfolio of data, technology, process, and people. Indeed, many people (such as [David Linthicum](http://weblog.infoworld.com/realworldsoa/archives/2009/01/burton_group_as_1.html), [Eric Roch](http://it.toolbox.com/blogs/the-soa-blog/is-soa-dead--29180), [JP Morgenthal](http://apsblog.burtongroup.com/2009/01/what-ive-learned-from-annes-blog-entry.html), and the ongoing debate on [InfoQ](http://www.infoq.com/news/2009/01/is-soa-dead)), for a number of years now, have been cataloguing why most enterprise SOA efforts fail miserably.

In general, I think the community is coming to the realization that SOA really is an architectural approach, not a set of technologies to implement. From that perspective Microsoft actually has been spot-on in terms of not offering “SOA”-branded products, but instead advocating customers to carefully design and build the right type of SOA for their organizations.

While there are many, many identified technical reasons why most SOA projects don’t succeed, [Mike Kavis](http://www.kavistechnology.com/blog/?p=440) in his post has articulated one perspective nicely at a high level (just summarizing his list here):
- We think process is a bad thing and it slows us down 
- We are impatient 
- We don’t understand what an architect really is 
- We don’t understand what architecture really is 
- We lose sight of the value and argue semantics 
- We lack leadership skills and emotional intelligence 

This highlights one area why SOA hasn’t been successful: the human factor. But this doesn’t only apply to SOA; it’s just that the SOA requirements for organizational transformation and consistency amplify issues associated with the human factor. So what aspects of the human factor that make SOA difficult to implement? 

## Lack of patience, persistence, and perseverance

I think this is applicable on many levels. SOA requires a long-term, incremental build approach, but many projects are required to justify immediate or short-term ROI. Or from a different perspective, people just naturally expect to see some form of immediate benefits, and lose interest/motivation when the reality of SOA hits after the first few initial projects, which are often ESB-driven infrastructure optimization efforts, or point-to-point integration efforts. The lack of immediate business agility and cost savings gives people excuses to question the approach, reduce level of support, etc.

There is the aspect of jumping on the bandwagon simply because SOA was the acronym du jour and that it seemed smart to talk about it, without investing sufficient research, discipline, and due diligence to do it right. Of course, those who are impatient to jump on the bandwagon would just as (if not more) quickly to jump off at the first sign of trouble. There was sufficient intention or willingness to invest in SOA endeavors, but the impatience of not acquiring necessary expertise resulted in failures.

And truth is, SOA is not easy. Many organizations lose sight of the most important aspect of SOA - “how” to do SOA, not “what” we do SOA with. To many organizations it just seems simpler to follow marketing hype and implement products that are branded as SOA suites and think that an SOA can be constructed using the new infrastructure.

## Resistance to change

People are naturally resistant to change, especially tough changes like SOA. Large organizations stand to gain more from SOA, but at the same time, those large organizations that have operated for many years in traditional functional silos have always resisted enterprise-level efforts that require them to build more dependencies on shared resources.
And SOA meant changes across all aspects of IT disciplines as we know. Operationally, traditional SLA management processes need to be adapted as downstream systems may need to inherit availability and performance requirements from upstream systems. Design-wise, it’s not just about exposing functionality as services, but more in the context of how a function is useful from the enterprise’s perspective; but that requires a higher level of collaboration beyond one department’s development teams.
Also, distributed computing is not simple. When we build process-level dependencies on other systems, efforts required to troubleshoot issues that one does not have full control over become magnitudes more challenging. This requires a major adjustment from the ways IT teams work today, and in those cases it’s often easier to point the finger at others first.

## Organizational dynamics

The above aspects often apply to individuals. But when we look at an organization as a whole, the effects are also amplified. SOA requires a higher level of collaboration between teams in an organization. Each team or department used to having a higher level of autonomy in terms of managing their budgets, schedules, clients, technology, etc.; relatively independently from other teams. How to find the right balance between organizational consistency and flexibility with sufficient local autonomy, is unfortunately in itself requiring a uniform understanding and approach within the organization.
And politics. Not everyone likes to work with everyone, and individuals used to be relatively shielded within their own teams/departments/silos. But SOA requires breaking down the walls of silos, and can expose people more to personalities they may not like to work with, causing more contention among people. If not managed carefully, such as not positively reinforcing the correct behaviors, this can more quickly send the wrong signals to workers and hinder progress.
Lastly, strategic thinkers who understand what it takes to do SOA, tend to be the minority in today’s IT organizations which typically focus on tactical goals and are also measured as such. It’s just difficult for a few individuals to influence and steer an organization to adapt new changes.

## So what now?

Thus it’s the “how” we do SOA that is the most important. It is the architectural disciplines, organizational cohesion, strategic leadership, etc. that most significantly impact the outcome of SOA efforts. And from that perspective the architectural principles of service-oriented architecture are still sound. In fact, as many people are already jumping into the next new big things such as cloud computing, “service”-oriented or driven concepts and considerations become much more important than before. Furthermore, cloud computing, in my opinion, has to do more about services than simply moving existing on-premises infrastructure into a utility-based cloud.

Perhaps it’s time to take a hard look at each SOA effort and ask the hard questions. Is it really meaningful, or valuable, to do SOA for your organization? Does your enterprise really need real-time process-driven integration, or traditional data integration, or a hybrid model, can suffice? Can people in your organization work collaboratively towards common goals and standards? Does your organization have what it takes to undergo and withstand such transformation? And so forth.

This doesn’t mean we should stop doing SOA (and regardless of what name we use to call it), but we should do it for the right reasons, and do it right. And more importantly, having the right people in the right places to see the plan through. This means having the right skills to plan and lead an organization to transform all aspects of data, technology, processes, and people (in knowing how to deal with the human factors mentioned above). There are still very significant benefits that SOA can bring, evident in the few organizations that have been successful with it.

Another lesson that can be learned from this ongoing discussion is that, SOA was deemed unsuccessful because it presented very significant gaps to the way existing IT organizations work today (such as what [Dana Gardner](http://blogs.zdnet.com/Gardner/?p=2772) mentioned in his post). However, we have to be careful in thinking that “abandoning SOA” and moving on to the next big thing – cloud computing, will solve all of our issues (doesn’t that sound eerily familiar?). It is evident that these gaps present such large gaps to many organizations, that the organizational aspects become the biggest impediments to progress. As technologists it is easy for us to say that the next major innovative technology trend will bring about sweeping changes and transformational benefits. But the reality is, cloud computing, as an extension of SOA, will require even more maturity and competencies in working with SOA to implement successfully. Indeed cloud computing presents a more prominent influencing factor to transform legacy IT, but it won’t make it any easier than SOA did. Organizations that want to take advantage of these transformative technology trends need to not only understand the technologies involved, but really pay attention to planning the organizational and people side of the endeavors.

(originally publishsed at <https://blogs.msdn.microsoft.com/dachou/2009/01/09/soa-end-of-life-2009-01-01/>)
