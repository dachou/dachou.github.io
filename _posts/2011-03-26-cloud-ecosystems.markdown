---
layout: post
title:  "Rise of the Cloud Ecosystems"
date:   2011-03-26 12:00:00 -0700
---

I had the opportunity to participate at this year’s [CloudConnect](http://cloudconnectevent.com/) conference, with my session on [Building Highly Scalable Applications on Windows Azure](http://www.slideshare.net/davidcchou/cloudconnect-2011-building-highly-scalable-java-applications-on-windows-azure), which is mostly an update from my earlier presentations at JavaOne and Cloud Computing Expo. I was pleased to learn that the cloud-optimized design leveraging distributed computing best practices approach, aligned well to similar talks by well-known cloud experts from Amazon, Google, etc. A more detailed discussion on this topic can be found in my earlier post - [Designing for Cloud-Optimized Architecture]({{ site.baseurl }}{% post_url 2011-01-23-designing-for-cloud-optimized-architecture %}).

![Amazon](/assets/20110326-amazon.png)

One of the major takeaways I had from the conference, was the focus on ‘cloud platforms’ (or platform-as-a-service generally) messaging, further reinforcing the platform view of cloud computing, as opposed to the infrastructure-level perspectives, or mixed views around the popular SaaS, PaaS, and IaaS service delivery models.

It started with Werner Vogels in his keynote presentation. Werner said, “it is all about the cloud ecosystem”, that “everything are cloud services; everything as a cloud service”, and “not constrained by any model”. And “let a thousand platforms bloom”, where “ecosystems grow as big as possible”. This implies that the popular models (e.g., SaaS, PaaS, IaaS) are irrelevant, because everything are simply services that we can consume, and these services can span the entire spectrum of IT capabilities as we know, and potentially more.

![Infrastructure as a service](/assets/20110326-iaas.png)

It is interesting to see how the platform messaging evolved over the past few years. For instance, Werner Vogels used to refer to Amazon Web Services as “Infrastructure as a Service”. However, I think Werner Vogels has always advocated the platform view, similar to Gartner’s notion of “application infrastructure as a service”, instead of the overused IaaS (infrastructure-as-a-service) service delivery model (as popularized by [NIST’s definition of cloud computing](http://csrc.nist.gov/groups/SNS/cloud-computing/cloud-def-v15.doc)). Perhaps, it was also because many people started incorrectly referring to Amazon Web Services as IaaS and not seeing the platform view, that Werner chose to clarify that models are irrelevant and “it is all about the cloud ecosystem”.

I also belong to the camp that advocates the platform view, and the further ecosystem view of cloud computing. The platform and ecosystem views of cloud computing represent a new paradigm, and promote a new way of computing. Though I think the SaaS, PaaS, and IaaS classifications (or service delivery models) still have some uses too. They are particularly relevant when trying to understand the general differences and trade-offs between the service delivery models (as defined by NIST), from a layers and levels of abstractions perspective.

![Cloud Models](/assets/20110326-cloudmodels.png)

Perhaps, what we shouldn’t do, is to try to fit cloud service providers into these categories/models. As often, a particular service provider may have offerings in multiple models, have offerings that don’t fit well in these models, or it’d be over-simplifying to refer to cloud platforms, like Amazon Web Services, Google App Engine, Windows Azure platform, etc., strictly in this platform-as-a-service definition. These platforms have a lot more to offer than simply a higher-level abstraction compute service.

## Cloud Platforms

As Werner Vogels said, “cloud is actually a very large collection of services”, cloud platforms aren’t just a place to deploy and execute workloads. Cloud platforms provide the necessary capabilities, delivered as distinct services, that applications can leverage to accomplish specific tasks.

Amazon Web Services has always been a cloud platform; today it is a collection of services that provide capabilities for compute (EC2, EMR), content delivery (CloudFront), database (SimpleDB, RDS), deployment and management (Elastic Beanstalk, CloudFormation), e-commerce (FWS), messaging (SQS, SNS, SES), monitoring (CloudWatch), networking (VPC, ELB), payments and billing (FPS, DevPay), storage (S3, EBS), support, etc. It is not just a hosting environment for virtual machines (which the popular IaaS model is more aligned with). In fact Amazon Web Services released S3 into production (March 2006) before EC2 (limited public beta in August 2006, removed beta label in October 2008).

Similarly, Microsoft has been using the platform-as-a-service messaging when describing Windows Azure platform, but it is also about the collection of various capabilities (delivered as services). For example, below is a visual representation of the application platform capabilities in Windows Azure platform that I have been using since 2009 (though the list of capabilities grew over that period):

![Cloud platform capabilities](/assets/20110326-platformcapabilities.png)

And below shows how those capabilities are delivered as services and organized in Windows Azure platform.

![Azure cloud services](/assets/20110326-azureservices.png)

This is important because the platform view is one of the major differentiators of cloud platforms when compared to the more conventional outsourced hosting providers. When building applications using hosting providers (or strictly infrastructure-as-a-service offerings), we have to incur the engineering efforts to design, implement, and maintain our own solutions for storage, data management, security, caching, etc. In cloud platforms such as Amazon Web Services, Google App Engine, and Windows Azure platform, these capabilities are baked into the platform and available as services that are readily accessible. Applications just need to use them, without having to be concerned with any of their underpinnings and operations.

An analogy can be drawn from high-level differences between getting food products from Costco to put together a semi-homemade meal, versus getting raw ingredients from a supermarket and prepare, cook, and finish a fully-homemade meal. 🙂 The semi-homemade model offers higher agility (less time and efforts required to put together a meal and to scale it for bigger parties) and economy of scale in Costco’s case, while the fully-homemade model offers more control.

Another distinction between cloud platforms and typical IaaS offerings, is that cloud platforms are more of a way of computing – a new/different paradigm; whereas IaaS offerings are better aligned towards hosting scenarios. This doesn’t mean that there are no overlaps between the two models, or that one is necessarily better than the other. They are just different models; with some overlaps, but ideally suited for different use cases. For cloud platforms, ideal use cases are aligned to net-new, or greenfield development projects that are cloud-optimized. Again, hosting scenarios also work on cloud platforms, but cloud-optimized applications stand to gain more benefits from cloud platforms.

## Cloud Ecosystems

The cloud ecosystem view takes the cloud platform view one step further, and includes partners and third parties that enable their services to participate in an ecosystem. The collective set of capabilities from multiple organizations and potentially services spanning multiple platforms and cloud environments together form an ecosystem that feeds and builds upon each other (in composite, federated, application models), and generating best practices and reusable processes, communities, etc. This can also be viewed as a natural evolution of platform paradigms, when drawing inference from other models where the iterations typically evolved from technology maturity, critical mass in adoption, and then building ecosystems. The platform with the largest and most diverse ecosystem, gets to ride the paradigm shift and enjoy a dominant position for that particular generation.

The Web platform stack model I discussed back in 2007 is one way of looking at the ecosystem model (apologies for the rich color scheme; I was going through a coloring phase at the time).

![Web platform stack](/assets/20071201-WebPlatformStack.png)

In essence, a cloud ecosystem itself will likely have many layers of abstractions as well; one building on top of another. One future trend in cloud computing may very well be the continued climb into higher levels of abstraction, as differences and complexities at one level often represent development opportunities (e.g., for specializations, consolidations/aggregations, derivations, etc.) at a higher level.

Ultimately, cloud platforms enable the dynamic environments that support the construction of ecosystems. This is one aspect inherent in cloud platforms, but not as much for lower-level IaaS environments. And as the ecosystems grow in size and diversity, the network effect (as discussed briefly back in 2008) will contribute to increasingly intelligent and interactive environments, and generate, collectively, tremendous value.

