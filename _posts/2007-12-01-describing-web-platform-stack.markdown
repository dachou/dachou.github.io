---
layout: post
title:  "Describing Web Platform Stack"
date:   2007-12-01 10:00:00 -0700
---
(originally published at [https://blogs.msdn.microsoft.com/dachou/2007/12/01/describing-web-platform-stack/](https://blogs.msdn.microsoft.com/dachou/2007/12/01/describing-web-platform-stack/))

**Context**

In an [earlier blog post]({{ site.baseurl }}{% post_url 2007-11-25-web-2-0-a-platform-perspective %}) I talked about "Web as a Platform" (in Web 2.0's context) and briefly described a layered and componentized perspective in looking at the Web platform in general. And I thought it would be more clarifying to illustrate what a Web platform stack might look like, so this post is intended to describe (not define) a stack view of the Web platform.

Plus, the evolution of this stack is the result of collective innovation contributed by many brilliant minds, and not driven by any single entity. Just as Eric Schmidt had said, "don't fight the Internet", I also don't think we need to model the Web after a specific prescribed framework. Rather, just allow the collective consciousness continue to innovate organically.

Thus this is a description of the Web platform (not a definition), as it is merely an attempt at categorizing the observed patterns and trends, and their relationships and dependencies, in the Web 2.0 phenomenon, into a structured context. There are many ways to describe and categorize these patterns, so this view is not necessarily exact and accurate, but hopefully it can provide some clarifications into the way Web is evolving.

**Architecture of the Web**

Below is a high-level rendering of the layered components architecture view of the Web platform stack:

![Web platform stack](/assets/20071201-WebPlatformStack.png)

The choice of words used is questionable, but the intention here is to highlight the trends and patterns (and their relationships) and hoping to effectively convey the concepts, without spending the time to make sure they are semantically accurate.

Just as I mentioned in my earlier blog post, layers towards the bottom of the stack are progressively closer to raw data and IT architectures, and layers towards the top are closer to people. In general, this layered stack view is used as I think lower layers serve as platforms that encapsulate the underlying complexities and provide abstraction and support to the upper layers. Even though this also kind of describes the evolutionary path (or a maturity model) of the Web in the past few years, I think this stack view is relevant as innovation is still occurring across this entire view.

Some examples to help clarify (nowhere near a comprehensive list; just intended to illustrate the categorizations):

Infrastructure: 
- Standards - XML, HTML, CSS, SOAP, REST, Atom, RSS, BitTorrent, HTTP, SMTP, FTP, SMS, VoIP, etc. 
- Tools - LAMP, WISA, JavaScript, .NET, Java, Visual Studio, Eclipse, etc. 
- Media - video streaming, podcasts, vcasts, electronic gaming, interactive TV, Microsoft IP TV, Microsoft Media Center 
- Runtimes - hosting environment, servers, desktops, browsers, clients, mobile devices, Microsoft Xbox, Sony Playstation, Nintendo Wii, Adobe AIR, Microsoft Silverlight, etc. 
- Networks - Internet, Wi-Fi, VPN, WAN, cellular, wireless LAN, DSL, FiOS, etc. 

Foundation:
- Utilities - Amazon EC2, programmableweb, etc. 
- Data - Amazon S3, Google Base, Microsoft Astoria, etc. 
- Storage - Google GDrive, Windows Live Skydrive, XDrive, DriveHQ, Box.net, Elephant Drive, etc. 
- Messaging - Amazon SQS, Microsoft BizTalk Services, etc. 
- Identity - Windows Live ID, Google Accounts, Yahoo! Accounts, OpenID, etc. 

Framework:
- Personalization - My Yahoo!, iGoogle, Netvibes, Windows Live, bookmarks, favorites, etc. 
- Transformation - Microsoft BizTalk Services (part of Don Ferguson's description of the "Internet Service Bus") 
- Composition - Yahoo! Pipes, Google Mashup Editor, Microsoft BizTalk Services, etc. 
Orchestration - Microsoft BizTalk Services (part of Don Ferguson's description of the "Internet Service Bus") 
- Privacy - TBD; in general, interoperable services to give users control over what parts of their online presences to share and what not to share 

Applications:
- Information - Google Analytics, Google Trends, MSN, Yahoo! News, Yahoo! Finance, Upcoming, etc. 
- Visualization - Google Maps, Virtual Earth, Yahoo! Maps, Google Gadgets, Windows Live Gadgets, Vista Sidebar Gadgets, mobile clients, etc. 
- Commerce - Amazon, eBay, Paypal, Google Checkout, MSN Shopping, Microsoft Points, etc. 
- Monetization - Google AdSense, Google AdWords, Microsoft AdCenter, pay-per-click, cost-per-action, impressions, etc. 
- Accessibility - TellMe, Google Translate, Live Search Translator, services for the visually impaired like Google Accessible Search, plusmo, ZapText, etc. 

Integration:
- Search - Google Search, Yahoo! Search, Ask, Windows Live Search, etc. 
- Distribution - Facebook Platform, Microsoft Popfly, etc. 
- Aggregation - Newsgator, Bloglines, Rojo, NetNewsWire, My Yahoo!, Windows Live, iGoogle, PageFlakes, etc. 
- Syndication - Twitter, Jaiku, Pownce, Facebook Newsfeed, Feedburner, Technorati, etc. 
- Portability - Gadgets, Widgets, Google OpenSocial, etc. 

Participation:
- User Content - blogs, wikis, reviews, photo sharing, Blogger, WordPress, LiveJournals, Wikipedia, CrowdRules, Flickr, Youtube. Epinions, Urban Dictionary, Trip Advisor, eHarmony, Match, etc. 
- Communities - MySpace, Facebook, Orkut, hi5, Bebo, Windows Live Spaces, Friendster, LinkedIn, World of Warcraft, Xbox Live, Second Life, etc. 
- Folksonomies - del.icio.us, Digg, reddit, Simpy, Furl, Netvouz, etc. 
- Collaborative Filtering - Amazon, half.ebay.com, NetFlix, TiVO, Last.fm, StumbleUpon, etc. 
- Mashups - Microsoft Popfly, JackBe, etc. 

Interaction (emerging):
- Social Graphs - capability to enable social network analysis and moving towards mapping physical relationships 
- Collective Intelligence - capability to comprehend and extract meaning from composite/aggregate communities 
- Microformats - creation of various metadata formatting approaches to add contextual relationships 
- Semantic Relationships - adding meaning and contextual mapping to various forms of content available on the Web 
- Implicit Networks - frameworks for capturing and analyzing dynamic aspects of user activities on the Web 

Interpretation (futures):
- Derived Intelligence - a form of artificial intelligence derived from collective intelligence to aid predictive analysis 
- User Intent - discernment of user intentions based on historical user activities, responses, and collective trends and patterns 
- Dynamic Relationships - ability to map dynamic aspects between user activities throughout the Web 

In general, each component in each layer is worthy of a separate detailed analysis, and only a minor fraction of things that are examples of a particular category have been listed. Though the intention is to show that each site or service individually is not representative of the layer component; it is the network effects created by the collection of sites and services in that category. Similarly for the layers in the platform stack, it is the aggregation of individual components that really exemplify the characteristics of that layer.

As a result, we can see that each layer in this stack view has dependencies on the services offered in the underlying layers. And each layer itself provides a level of abstraction and support to the layers above. Thus architecting solutions using the Web as a platform is quickly becoming a process of choosing a target layer (where the solution will reside), and choosing the appropriate combination of support services from the underlying layers.

This view can also be helpful in visualizing general trends of innovative development on the Web, and identify potential spots where opportunistic developments can occur, and areas where they have been turned over to systematic developments. For example, the current state (as of this writing) is that mainstream efforts can be categorized as focused in the "Participation" layer, and is where many of the opportunistic developments are being turned into systematic ones (basically, gaining maturity). The "Interaction" and "Interpretation" layers are considered to be the subject of the next Web (or Web 3.0), and is where much of the research & development efforts are focused in.

One fundamental aspect is that, the Web platform is created and maintained by the collective wisdom contributing to it. It is too big and too diverse for any one entity to own, even though many organizations have investments in multiple areas, and some more than the others. But it is interesting to see how this view of the Web platform is taking shape, based on the inter-dependencies and (almost "symbiotic") relationships established between the clusters of sites and organizations operating on the Web.

**Hypothesis**

The general concept here is that, Web 2.0 applications are taking on a new form. They are composite applications in nature, and increasingly can be created and hosted completely in the Web (cloud), without any dedicated on-premise infrastructure. And they are increasingly being implemented at higher levels of abstraction (moving up the stack).

For established enterprises, this marks a shift in Web application models. From approaches to open up enterprise data silos and providing value-added services to customers ("Applications" layer aspects), to migrate to a model where various higher-level components of the Web ("Integration" and "Participation" layer aspects) can be integrated and leveraged to connect to the communities. For emerging businesses, it is now possible to quickly establish an initial online presence by completely building on the cloud-based Web platform, while looking to add differentiating values with a variety of options (such as dedicated on-premise solutions).

From a user participation perspective, lower layers are progressively closer to people with higher technical expertise, but are populated by smaller communities. On the other hand, upper layers are progressively closer to larger communities as barriers to entry, from a technology perspective, are increasingly lower. This aspect demonstrates the power of network effects in enabling the participation age, and fueling the explosive pace of innovation towards creating a Web that connects/involves more people and is more relevant and intelligent.

![Web as a Platform](/assets/20071201-WaaPCommunities.png)

Certainly, areas where boundaries are being pushed may still sound like science fiction, and it's fun to imagine that new breakthroughs will bring about sea changes that will overthrow all conventional wisdom. The blogosphere already has tons of speculations in that respect. Though I believe "could" does not equate to "should", such that change for change sake will not add value; only changes that lead to better outcomes will gain adoption. Thus my assessment is that, significant changes are surely imminent, but conventional wisdom will also not cease to complete irrelevance. Eventually, when the pendulum settles, we usually see a hybrid world, with some changes more dominant, and some changes less. The Web is a place where rapid changes are occurring, and as architects and strategists, using a pragmatic viewpoint when facing these changes may help us better plan the migration path between current and future states.
