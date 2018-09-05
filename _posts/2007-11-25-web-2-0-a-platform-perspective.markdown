---
layout: post
title:  "Web 2.0 – A Platform Perspective"
date:   2007-11-25 10:00:00 -0700
---

"Web as a Platform" has been a much discussed topic since Tim O'Reilly used it as a tagline in the first Web 2.0 conference back in October of 2004, then described in more detail in a [2005 article](http://www.oreillynet.com/lpt/a/6228), and the subsequent "[Mind Map](http://en.wikipedia.org/wiki/Image:Web_2.0_Map.svg)" graphic:

![web 2.0 mind map](/assets/20071125-web20.jpg)

Since then many interpretations of the "Web platform" have existed, ranging from technical perspectives that focused on tools such as AJAX, RSS, REST, SOAP, mashups, composite applications; user-generated content and collective intelligence such as Wikipedia, Youtube; social bookmarking/syndication such as del.icio.us, Digg; to social networks such as Facebook, Myspace, etc. Just to list a few, but the list of sites and categories of sites that exemplify Web 2.0 principles has undergone an explosive growth in the past few years.

Collectively, the rich cluster of "Web 2.0" sites on the internet form a services foundation from which applications and functionalities can be built upon, without needing any additional dedicated infrastructure. This marks a significantly different approach from "Web 1.0" site implementations where each organization has to procure dedicated hardware, software, hosting environment, etc. in order to provision a new application on the internet. As a result, the collection of cloud-based services form a new kind of "platform" to create a new breed of applications.

**Understanding Web as a Platform**

Without making this yet another attempt at trying to define the specifics of Web 2.0 (or even [Web 3.0](http://en.wikipedia.org/wiki/Web_3.0) for that matter) and the internet platform, delegating it to those who focus on semantics, I think we can look at "Web as a Platform" in its broadest terms. That is, a platform that provides some sort of framework which allows people to build stuff upon, while encapsulating (or hiding) some of the underlying complexities.

But this doesn't point directly to technical solutions; it really encompasses many categories of "stuff" (such as media, social interactions, implicit relationships, semantic connections, monetization methods, etc.) that can be leveraged and implemented on the Web today. I liked how [Fred Wilson](http://www.readwriteweb.com/archives/defining_web_as.php) said it:

> I believe the web is a platform. And that everything we need for an open ad market, or an open data architecture, or frankly most anything else, is available on the "web platform" today.

So what can we do with the Web platform? There are many perspectives on this as well. Such as [Marc Andreesen's](http://blog.pmarca.com/2007/09/the-three-kinds.html) "layered" perspective:

> Level 1 - API access - Flickr, Delicious, Twitter, etc. \\
> Level 2 - API plug-in - Facebook \\
> Level 3 - Runtime environment - Ning, Salesforce.com, etc.

And [Alex Iskold's](http://www.readwriteweb.com/archives/web_platform_primer.php) "building blocks" perspective:

> Storage Services - Amazon S3, GDrive, Windows Live Skydrive, etc. \\
> Messaging Services - Amazon Simple Queue Service, BizTalk Services, etc. \\
> Compute Services - Sun Grid \\
> Information Services - Amazon E-Commerce, Yahoo! Answers, Virtual Earth, etc. \\
> Search Services - Google Search API, Alexa Search Platform, Live Search, etc. \\
> Web 2.0 Services - del.icio.us, Flickr, Basecamp, etc.

Again, without questioning the validity of these categorizations used (as there are lots of discussion about that as well), I think from a general sense, both perspectives are valid. I think that building blocks do exist, but at the same time, there are multiple layers of building blocks (or categories) in the Web platform.

What this means, is that building blocks in each layer can be utilized in various combinations/permutations to create the next layer up. These layers span between two extremes - information and people. The layers closer to information consist of Web application platforms as we know today, such as ASP.NET, Silverlight, LAMP, Java, Ruby on Rails, etc.; that require more expert knowledge in development and technology but smaller parts of the overall population. The layers closer to people are still being formed as we speak, but in general they rely on higher forms of abstraction that provide services closer to our lives, while enabling the broad reach of larger pools of audiences (consumerization and democratization of technology comes to mind). And today we are seeing higher and higher layers of platforms being created that allow people to connect, to organize, to find and use resources, to be social, and to basically "live" on the Web.

Of course, the word "platform" is being used very loosely today, and new "platforms" and layers of platforms are being created almost on a daily basis. [Marshall Kirkpatrick](http://www.readwriteweb.com/archives/hyped_new_platforms_explaining.php) took a real brief look at some of the most hyped new platforms today. For example, the most recent and significant incarnations of higher-level Web platforms are probably [Facebook Platform](http://www.facebook.com/platform_tour.php) and [Google OpenSocial](http://code.google.com/apis/opensocial/).

From a platform layer perspective, the Facebook Platform and Google OpenSocial, even though aimed at doing different things (lots of debate on this too), are built on top of other existing layers. Applications built on top of the Facebook Platform use a combination of traditional Web app technologies like HTML, CSS, JavaScript, XML, etc., but their benefits are derived from building blocks available on the Facebook Platform, in the form of mashups of external services building blocks, explicit foundation blocks (such as News Feeds, Status, Events, FBML, FQL, configuration and provisioning systems, etc.), and implicit foundation blocks (social graphs, software distribution/dissemination channel, monetization, 50+ million and still growing user base, etc.). A major characteristic of this platform is that it is very easy to develop against, which democratizes development and allows more and more people to participate in the social experience. In essence this platform furtherly narrows the gap between technology and people (thus categorized as a higher-layer platform). This resulted in a wildly viral and vital platform that has accounted more than 5,000 applications deployed today and growing exponentially.

From a higher level, it seems that a "Web OS" of some sort is starting to take shape, as we can draw many parallels to the layered, subsystems and componentized approaches in modern computer operating system and software architectures. But I am not yet sure that it would be of value to try to apply traditional thinking in defining a "standard" Web platform stack, by needlessly preempting more knowledgeable people, and risk further defragmenting the evolution.

In general though, by today we can definitely see the Web maturing as a very viable platform. News such as Amazon S3 exceeds 99.99% uptime should remove most doubts about the reliability of cloud-based services. But I think it is a platform with a spectrum of choices (layers and building blocks) where people with different skillsets can look to leverage and add value. The choices available in the full spectrum are all relevant, despite some idealists' claim that newer and higher-level models (such as higher layers of the platform used in the context of this post) will completely commoditize and subsume older and lower-level models. I tend to think that, while it is true that more and more attention will be focused on newer and higher-level models, we will continue to see lots of innovation on the lower-level layered platforms. We will just see that more and more people will be involved in the overall ecosystem, with a large infusion of participants with non-technical skillsets increasingly more involved at the higher levels. This I think is the true goal of Web 2.0, connecting people and democratizing/bridging the technology chasm.

**What's Next?**

It's always interesting to try to take a peek at what may be possible in the future.

*Democratization in software development* - Recent advances in the Web platform (raising layers of abstraction), model-driven architectures, etc., will increasingly simplify software development efforts for the higher level platforms. Two very notable examples are Yahoo! Pipes and Microsoft Popfly.

*The Implicit Web* - Increasing specialization in making sense of the dynamic aspects of user behaviors and activities in the online world. For example, search engines to finally grasp user intent (via click streams, combinational media consumption habits, etc.). This is also an area where the Facebook Platform may be able to glean from the reactions its applications can elicit from the members, based on the static social graphs.

*Privacy Controls* - With so much attention on enabling the "read-write" Web, and increasing openness, a need for better privacy control will inevitably arise. Web idealists argue that traditional data silos (or intellectual property as we know today) will need to be opened up and interoperate in the new world. Again, I believe a hybrid model somewhere between the two extremes (of fully open and completely closed architectures) usually work out better to the benefit of its users. From this perspective, yes the highly protected enterprise data silos today will need to open up, but should be just enough to add value for the users. To do that, some kind of interoperable privacy controls is required.

*Ubiquitous Access w/ Rich User Experiences* - A consistent and seamless experience for people accessing their information, applications, and services, across a full spectrum of connected devices and systems. At the same time, highly targeted user experiences implemented for the appropriate form factors are available to take advantage of the latest hardware and device innovations.

There are many more, such as the data/semantic Web, evolutionary intelligence, changes in social trends, etc. It'll be interesting to see how things pan out in this space.

(originally published at <https://blogs.msdn.microsoft.com/dachou/2007/11/25/web-2-0-a-platform-perspective/>)

