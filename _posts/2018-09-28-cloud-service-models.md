---
layout: post
title:  "Cloud Service Models (IaaS, PaaS, SaaS) Diagram"
date:   2018-09-28 12:00:00 -0700
---

I'm guessing most of us have seen a version of the diagram that compares the cloud computing service models (IaaS, PaaS, SaaS) and on-premises environments, sometime within the past few years? You know, the one that uses a visualization of four software (layer cake) stacks to describe the differences between infrastructure, platform, and software "-as-a-service" models as described in [The NIST Definition of Cloud Computing](https://csrc.nist.gov/publications/detail/sp/800-145/final)?

![cloud service models](/assets/20110326-cloudmodels.png)

This is the (boring) story/recap of how this diagram came into existence. 😉

## 2008: Birth of Azure

At the time of this writing, it is almost 10 years since the initial announcement of Microsoft Azure (at the time named "Windows Azure"), [by Ray Ozzie at the Microsoft Professional Developers Conference 2008](https://channel9.msdn.com/Blogs/pdc2008/KYN01) (PDC08) in Los Angeles on October 27, 2008. If you recall, at the time this is something mostly inconceivable that Microsoft would do. Afterall, only the cool kids on the block, Amazon and Google, seemed to be interested in cloud computing; plus take into account of the observation that a subscription-based revenue model potentially cannibalizes many of Microsoft's existing license-based products.

After the announcement, there was an incredible amount of interest in the community to learn about Azure. According to my notes, I alone had more than 300 meetings with organizations of all sizes in a 6-month period following the announcement.

In one of the slide decks I used at the time (around November 2008 timeframe), there was this diagram (can be found on [Slideshare dated Nov. 19 2008](https://www.slideshare.net/davidcchou/microsoft-and-cloud-computing-presentation/5-On_premises_vs_in_the)):

![20081119](/assets/20180928-cloud-service-models-20081119.png)

This was used to explain the platform-as-a-service (PaaS) approach Azure implemented. As you recall, Azure at the time only had Web Roles and Worker Roles (classic cloud services as categorized today) as primary compute options. These being services that operate in the PaaS model, we needed to rationalize/justify the fundamental differences in the PaaS model, compared to how people understood on-premises IT at the time. This diagram helped to articulate the trade-offs between the well-known models at the time: on-premises, outsourced hosting, and the (new) public cloud environments.

## 2009: Concept Formation

The first diagram succinctly highlights the major differences and helped people recognize that PaaS is different from outsourced hosting and on-premises IT, but we needed to explain how and why as well. 

The idea was to create a visual representation of existing on-premises IT environments, and the cloud service models mapped in the same context, so that the differences can be highlighted on top of the commonalities (as opposed to explicitly stating them in words in the earlier diagram). Thus the 9-layers stack view was developed, using common, high-level IT infrastructure domains that can be carried consistently across all of the models. The specific layers were chosen as they exemplify some levels of separation of concerns, and to imply a traditional IT stove pipe stack representation, with some direct dependencies between stack layers, or design/operational abstraction.

After many iterations, this view was developed (implying that PaaS is more different and valuable than how IaaS is different from outsourced hosting), first published on my MSDN [blog (dated Jan. 13 2009)]({{ site.baseurl }}{% post_url 2009-01-13-cloud-computing-and-microsoft-platform %}):

![20090526](/assets/20180928-cloud-service-models-20090526.png)

(as a side note) The inter-layer dependency and separation of concern aspect is often lost when trying to use other models to visualize this stack relationship, such as [pizza-as-a-service](https://www.linkedin.com/pulse/20140730172610-9679881-pizza-as-a-service/) and [car-as-a-service](https://community.dynamics.com/365/financeandoperations/b/axtipsandtricks/archive/2016/07/14/what-is-cloud-and-what-are-iaas-paas-and-saas). To me these analogies make the diagram more interesting, but they ended up missing an important part of the context.

And the use of hot coloring (red slices) vs. cool coloring, and number of layers highlighted per model, were all intended to illustrate the differences (how everything on-premises is 'hot', but IaaS is less, and how PaaS is comparatively different with just one highlighted layer).

As this view gained traction, a version of it was published on [Slideshare (dated Jun 9 2009)](https://www.slideshare.net/davidcchou/patterns-of-cloud-applications-using-microsoft-azure-services-platform). Along with this car analogy which mapped to the same 3-column structure to help people relate to the impact of the differences in these models.

![analogy](/assets/20180928-cloud-service-models-20090526-analogy.png)

The talking points for this analogy were:
- On-premises: is like owning your cars - you can go anywhere you want at anytime (full **control**), in a fully-paid car make/model/color/trim of your choice, but you'd be responsible for its maintenance
- IaaS: is like a car rental service - you still can go anywhere you want at anytime, some limits in car choices, but you don't have to maintain the vehicles; just take the keys and go
- PaaS: is like public transportation - you are limited by available routes and schedules, but it's easy to use and pay-per-use (full **economies of scale**)

Fundamentally, this still mapped to the initial high-level trade-offs messaging between 'control' and 'economy of scale', but it is now visually easier to understand and helps facilitate a more engaged discussion during a presentation.

For the following months, from a visual design perspective, there was a shift starting to move away from 3D looking graphics (e.g., boxes with gradients, lighting, bevel, borders, shadows, effects, etc.) towards a flatter, simpler design. This diagram was also updated to reflect those trends ([Slideshare (dated Oct 17, 2009)](https://www.slideshare.net/davidcchou/windows-azure-platform)).

![20180928](/assets/20180928-cloud-service-models-20091027.png)

## 2010: Full Realization

By this time many people have seen this diagram, as its usage proliferated widely publicly, and within Microsoft, when we went "all-in" with the cloud, and the armies of Microsoft employees and partners started blogging and presenting about Azure. Among the many feedback received, was one from [Scott Kerfoot](https://www.linkedin.com/in/scottker/), who suggested to add a fourth column to represent Software-as-a-service (SaaS).

Adding SaaS also gave us an opportunity to update the layers definition a bit, plus we needed to differentiate PaaS and SaaS with more than one layer difference. Thus "Security & Integration" was removed as security concerns exist at all layers, and added "Data" underneath "Applications". Then "Databases", "Servers", and "Server HW" were changed to "Middleware", "O/S", and "Server"; respectively.

And then this view was created (dated Jan. 15 2010):

![20100115](/assets/20180928-cloud-service-models-20100115.png)

And then further flattening and simplifying the graphic design of the diagram, plus a few minor edits, such as changing "O/S" to "Operating System", and "On-Premises" to "Traditional IT" (as on-premises also incuded private cloud context so we needed to differentiate from that), we reached the final version shown below (same as the one at the top of this post). These versions was published and propagated via other sources, and as my presentation decks were mostly incremental technical detail updates, and so they were published to avoid too much duplication. It was later in 2011 that when I wrote about [cloud ecosystems]({{ site.baseurl }}{% post_url 2011-03-26-cloud-ecosystems %}) when I referenced this version below.

![20110226](/assets/20180928-cloud-service-models-20110226.png)

## Today

Progress moves fast in this industry. It was soon after 2011 that our conversations shifted from explaining and justifying PaaS, towards primarily deeper discussions and engagements about real projects, and lines between IaaS and PaaS started to blur. It was increasingly more about composing capabilities into cloud projects, regardless which 'cloud model' a particular implementation uses. Application projects were composing services and features built on IaaS and PaaS options. It was no longer IaaS or PaaS; it was IaaS AND PaaS. Furthermore, there was increasing maturity around hybrid cloud approaches so even the lines with on-premises environments were blurring.

Thus this diagram is no longer part of my standard cloud computing presentations. However, it continues to be referenced and used widely in cloud computing literature in many forms. Some of the core content has been updated frequently over the years, but it's interesting to see how this diagram is still being used by people today.

A simple image search on "iaas paas" would yield hundreds of hits from all kinds of sources around the world, and many kinds of variations and flavors, and in different languages. Some people claimed to have created this view, while some credited "the Internet"; though it's kind of funny to see how this unit of work took on a life of its own.

![image search](/assets/20180928-search-results.png)

