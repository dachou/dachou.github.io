---
layout: post
title:  "Cloud Computing as a New Development Paradigm"
date:   2010-07-20 12:00:00 -0700
---

A colleague pointed me to a blog post [Cloud this, cloud that](http://ztrek.blogspot.com/2010/07/cloud-this-cloud-that.html), which to me reflects the common perception around cloud computing that it is just another form of server hosting; a deployment/delivery model. Instead of simply trying to re-deploy existing software into the cloud, our opinion is that cloud computing also offers more, in terms of a new way of writing software that exploit cloud computing as a platform; especially when leveraging the new breed of cloud platforms such as Windows Azure.

Just sharing my brief feedback to that blog below; will provide more detailed thoughts on this topic in a later post.

Cloud is indeed what everyone’s talking about right now; kind of like SOA during its heyday but even bigger in magnitude because barrier to entry to cloud computing is a lot lower than SOA and it can yield tangible short-term benefits.

To the question “how much does a software development team need to know about the cloud, beyond how to deploy to it and integrate applications with cloud-based apps?”, to me it depends on what ‘cloud computing’ means to a development team. If cloud computing is just deployment and integration, more like outsourced hosting, then yes, there isn’t much a software development team needs to know.

However, we believe that is just the utility computing aspect, a delivery model, of cloud computing. To truly benefit from cloud computing, software development teams can look at cloud computing as a new development paradigm, and leveraging it as a new paradigm and lead to differentiated value.

Specifically, software that operate in cloud environments can be architected and written differently for the cloud than existing on-premises environments. Traditional n-tier development tends to focus on synchronous end-to-end transaction processing (tightly coupled) and locking concurrency control models, which typically lead to vertically integrated monolithic architectures that rely on clustering fewer and larger hardware to provide scalability/reliability. If we look at cloud computing as a development model, and design/architect towards distributed computing models, different design principles start to emerge. For example, multi-tenancy, eventual consistency (concurrency model), de-normalized and horizontally partitioned and shared-nothing data, asynchronous and parallel distributed processing, process redundancy and idempotency, service-oriented composition, etc.; these lead to horizontally scaling architectures that are consisted of a larger number of smaller and loosely coupled distributed components/services.

Cloud computing supports this type of architecture (especially prevalent in large web applications such as Facebook, Twitter, Google, etc.), and is required for applications that operate at Internet scale – those that need to process massive amounts of transactions or data. The ability to handle such high scale is not something that can be achieved with traditional monolithic architectures, and in fact, is becoming a very significant strategic and competitive advantage to those that can leverage it. This is the true differentiation aspect of cloud computing, and is what software development teams need to know.

(originally published at <https://blogs.msdn.microsoft.com/dachou/2010/07/20/cloud-computing-as-a-new-development-paradigm/>)