---
layout: post
title:  "Describing Cloud Computing"
date:   2008-07-25 12:00:00 -0700
---
(originally published at [https://blogs.msdn.microsoft.com/dachou/2008/07/25/describing-cloud-computing/
](https://blogs.msdn.microsoft.com/dachou/2008/07/25/describing-cloud-computing/))

Cloud computing, the buzzword du jour and hottest cliche in IT at the moment, is a source for extensive debates as well as general confusion. Just like the other buzzwords, SOA, Web 2.0, Software-as-a-Service (SaaS), "cloud computing" is a very general term, and there are many interpretations of what it means.

And just like those buzzwords, cloud computing represents the convergence of many other megatrends and evolutionary developments leading up to this point. For example, SOA, Web as a platform, SaaS, utility computing, grid architectures, on-demand computing, outsourced hosting, managed/application service providers, etc., can all be considered contributing components to cloud computing.

This slide from Gartner has a nice list of some common misunderstandings of cloud computing.

![gartner](/assets/20080725-gartner-cloud2.png)

So what is cloud computing then? Taking a similar approach to my last year's post on Web as a platform, a formal definition of cloud computing won't be attempted here. Instead, we will try to describe the emerging phenomenon by looking at the components and contributing aspects and patterns, as well as some of the current issues and challenges.

**Fundamental Aspects of Cloud Computing**

Again, this is just one way of looking at cloud computing, among many others. Basically, a couple of fundamental aspects I think are relevant:

- Service Delivery 
- Service Composition 
- Service Consumption 
- Economies of Scale 
- Network Effect 
- Ubiquity / Pervasiveness 

_Service Delivery_

The cloud has become an alternative means of delivering various types of capabilities as services. Software-as-a-service (SaaS) is one that receives a lot of attention, but from a cloud computing perspective, it can be any type of technology-enabled capabilities, delivered as-a-service. For example, virtualized storage, communication, compute capacity (utility computing), are all existing forms of capabilities delivered as services, but are not categorically defined as software capabilities.

In the SaaS space, Salesforce.com has been cited as one of the prime examples, as a complete end-to-end solution delivered as a service. Earlier examples include outsourced hosting providers, managed service providers, etc. Today the cloud-based delivery model is being applied across all types of scenarios, including delivering traditional desktop applications as cloud-based services, such as Google Apps and Zoho Office. Microsoft of course has its own set of cloud-based services as well.

_Service Composition_

Not all services are of the same type. In fact many types exist as well as many ways to categorize/describe them. They include infrastructure, platforms, building blocks, etc., that operate on a technical level, to finished services that users can interact with directly.

The fundamental aspect is that individual services can sometimes be integrated or composed or aggregated into higher-level services that perform a specific function available in the cloud. This is essentially the extension of SOA principles into the cloud, and enabling the [Web as a platform]({{ site.baseurl }}{% post_url 2007-11-25-web-2-0-a-platform-perspective %}).

![web platform stack](/assets/20071201-WebPlatformStack.png)

_Service Consumption_

Web browsers will continue to serve as the primary means of accessing cloud-based services. But the cloud does not dictate the use of browsers as the only means to do so. In fact, cloud-based services provide the ideal environment to enable users consume services from all kinds of interfaces and devices.

We are already seeing many vendors pushing the envelope beyond HTML-based browser interfaces. For example, on-line in-browser RIA platforms such as Adobe Flash, Curl, JavaFX, and Microsoft Silverlight, etc.; off-line desktop RIA platforms such as Adobe AIR, Google Gears, Yahoo Konfabulator, and Microsoft Live Mesh; and increasingly, mobile device platforms such as Apple iPhone, Google Android, Java ME, Adobe Flash Lite, Yahoo GO!, Microsoft Silverlight, etc.

The fundamental aspect is that, cloud computing enables a seamless and consistent service consumption experience regardless of the type of device or interface used at the edge. In addition, differentiated and specialized user experiences can be delivered to different types of devices and form factors.

_Economies of Scale_

The most effective design for cloud-based services use multi-tenancy architectures, and standardize on operational and management processes. This allows service providers to share costs between multiple users, which results in lowered overall cost of service. And as the scale of usage/adoption increases, so do the economies of scale. This is not limited to managing costs; monetization models behave similarly such as in the case of Google's search advertising business.

The cloud provides the ideal environment for service providers to leverage massively-scaled capabilities to achieve intended economies. But this does not mean all services providers have to plan for similar scales. For example, Salesforce.com's scale in terms of managing its userbase, is significantly different from the type of scale that Google or Amazon has to deal with.

_Network Effect_

The cloud is more than a huge collection of isolated services and islands of services. Its true power is unlocked when individual services become more inter-connected and inter-dependent. With increasing levels of interoperability, composability, data portability, semantic consistency, etc., the cloud moves away from disconnected services that require specialized integration efforts, to a dynamic system that is much more interactive and intelligent.

_Ubiquity / Pervasiveness_

The word cloud implies a level of ethereal ubiquity and pervasiveness. And cloud-based services should be provisioned such that users should not have to be concerned with how to access these services, or differences between platforms. In addition, details of the technical implementations, scaling options, etc. should be completely transparent to the users as well.

Users should be able to interact with cloud-based services in a consistent context, even when navigating between the public cloud and private clouds.

**Challenges and Issues**

Undoubtedly, cloud computing presents many disruptive forces to existing models of using on-premise and locally installed software and applications. But some questions are still relevant. For example,

- Who owns sensitive and confidential data? 
- How is SLA managed and enforced/guaranteed? 
- Regulatory compliance? 
- More potential points of failure? 
- Typical operational concerns, such as fine-grained control over security/privacy, governance, support for troubleshooting, overall performance, disaster recovery, planned downtimes, change management, etc. 
- Does it really cost less to users? 
- How will I differentiate? 

Another Gartner slide has a good list of common concerns.

![gartner](/assets/20080725-gartner-cloud1.png)

For example, some of the recent reported issues underscore the difficulty in maintaining massively-scaled cloud services (of course Microsoft had its share of outages too):

- [Amazon S3 outage rains on cloud-computing parade](http://resources.zdnet.co.uk/articles/comment/0,1000002985,39451066,00.htm?r=10)
- [Gmail outage, relying on Google too much?](http://tech.blorge.com/Structure:%20/2008/01/28/gmail-outage-relying-on-google-too-much/)
- [Google AdSense site suffers outage](http://www.webpronews.com/topnews/2008/03/10/google-adsense-suffers-outage)
- [Google App Engine goes down and stays down](http://www.techcrunch.com/2008/06/17/google-app-engine-goes-down-and-stays-down/)
- [Google Calendar outages anger users](http://www.computerworld.com/action/article.do?command=viewArticleBasic&taxonomyName=networking_and_internet&articleId=9073119&taxonomyId=16)
- [Google evaporates Docs and Spreadsheets cloud](http://www.theregister.co.uk/2008/07/08/docs_and_spreadsheets_goes_down/)
- [Google Finance Outage](http://www.webguild.org/2008/03/google-finance-outage.php)
- [Salesforce.com outage irks customers](http://www.itbusinessedge.com/blogs/hdw/?p=1639)

And a recent BusinessWeek article "[On-Demand Computing: A Brutal Slog](http://www.businessweek.com/print/technology/content/jul2008/tc20080717_362776.htm)" pointed out:

> "Funny thing about the Web, though. It's just as good at displacing revenue as it is in generating sources of it. Just ask the music industry or, ahem, print media. Think Robin Hood, taking riches from the elite and distributing them to everyone else, including the customers who get to keep more of their money and the upstarts that can more easily build competing alternatives."

And Nicholas Carr's post back in 2005 on "[The amorality of Web 2.0](http://www.roughtype.com/archives/2005/10/the_amorality_o.php)" succinctly points out the changes in monetization models in the shift towards the Web.

While we can expect that the industry as a whole will continue to move into the cloud, and gain more maturity in deploying cloud-based services, these fundamental questions and challenges will have to be addressed as well. Although, some issues inherent in highly distributed architectures will persist and need to be evaluated as trade-offs.

**Forward Looking Perspective**

It seems we are in a land-grab mode today, with organizations rushing towards the cloud, including Microsoft. Next we should expect to see the similar hype-boom-bust cycle play out, where many attempts will fade into non-existence, major consolidations occur in the market, and finally a handful of strong players remain standing and owning a major portion of the collective cloud.

However, when the dust (or the pendulum) finally settles, will we see cloud computing supplanting the "legacy" models? Most likely not, though cloud computing will become one of the viable options for organizations to choose from. And we can expect that there will not be a one-size-fits-all approach on a "right" way to decide between on-premises and cloud-based services. Just like all previous megatrends such as SOA and Web 2.0, each organization may have a different mix of options and the degree to which they are adopted.

Technically, we can anticipate advances towards context-aware computing as a convergence of semantic Web, data portability, derived collective intelligence, intent-driven systems, etc.; which should result in a much more intelligent and interactive cloud.


