---
layout: post
title:  "Cloud Computing and Software Clients"
date:   2008-07-25 12:00:00 -0700
---
(originally published at [https://blogs.msdn.microsoft.com/dachou/2008/07/25/cloud-computing-and-software-clients/](https://blogs.msdn.microsoft.com/dachou/2008/07/25/cloud-computing-and-software-clients/))

As the Web evolved, there has been countless proclamations that client-side software is dead or on its way out. Certainly, the staggering pace of innovation in Web application platforms and Web-oriented architectures, and associated mindshare shift towards Web development models, do show that client-side software is becoming less relevant than the heydays of client-server computing, at the very least.

And many people think that the move towards cloud computing also marks the inflection point where the desktop is becoming irrelevant, such that not just data, but everyday software applications and utilities are moving into the cloud too. And the Web browser becomes the new desktop that is ubiquitous and comes with the benefits of zero-footprint applications that can follow you wherever you go.

**As the Pendulum Swings**

At the same time, it seems we've reached a plateau where the focus has shifted from ensuring the availability (or accessibility) of capabilities in the cloud, to improving usability of cloud-based services.

In other words, as an industry, we have gotten sufficiently productive at developing high-quality Web applications delivered via browsers, and are starting to seek the traditional benefits of client-side software especially from a user experience perspective. Partly due to:

- The document-based HTML user interface model is reaching limits in terms of integrated user experiences 
- JavaScript and AJAX-rich implementations needing more sophistication are reaching complexity levels of desktop software 
- Downloaded on-demand and zero-footprint deployment/installation - Web applications still make use of client-side code and are increasingly balancing trade-offs between richness and performance (client-side, download size, network bandwidth, etc.) 
- Online applications requiring users to be on-line - bringing Web applications off-line still has its challenges; that is, Web applications don't automatically convert to good desktop applications 
- Creating capabilities beyond what the browser platforms provide means writing desktop software components that add complexity in integrating with Web applications
- RIA technologies extend the HTML model, but still restricted by the browser sandbox model

And a few signs in the blogsphere (i.e., "[Web App + Offline = Crappy Client App](http://www.furrygoat.com/2008/04/21/web-apps-offline-crappy-client-app/)", "[Maybe Microsoft is Right...](http://jeremy.zawodny.com/blog/archives/010199.html)") of this turn-around:

>Q: What do you get when you cross a browser application with the ability to go offline?
>
>A: A client application without any the goodness that the platform (be it Windows or OS X) has to offer.

**SaaS and Software Clients**

SaaS CRM vendor Entellium recently released a smart client and said it will phase out its existing browser-based product over the next 12 months. It was reported that the move helped boost sales, and cut customer acquisition costs by as much as 80 percent.

The smart client application looks very slick, and is built using Microsoft's Windows Presentation Foundation (WPF) technology:

![rave](/assets/20080725-rave-screenshot.jpg)

My colleague John Stame has also just worked with Sciformatix to implement a SaaS solution built on .NET, but also delivered multiple access points including a browser interface, a mobile device interface, and a .NET-based rich client:

![Sciformatix](/assets/20080725-Sciformatiximage.jpg)

And the well-known WPF-based New York Times Reader which was mentioned by [PC World as one of 2007's 100 best products](http://www.pcworld.com/article/131935-13/the_100_best_products_of_2007.html).

![nytimes](/assets/20080725-winvista_nyt_08.jpg)

These services are still delivered SaaS-style, with data and processes that are hosted in the cloud. But smart clients provide a more intuitive interface for users, while at the same time adding the much needed off-line capabilities. Plus, the decision doesn't have to be either/or or mutually exclusive; browser-based and client-based software can be implemented and deployed at the same time to provide a higher level of service to users, taking advantage of best of both worlds.

Of course, these cases still represent a rather small sample size of the general SaaS community, but they are good examples of leveraging the appropriate technology to differentiate and add value to customers.

**Software Clients Making a Comeback?**

Well, perhaps not completely; but it would be prudent to not ignore their value propositions. Basically, it is about improving usability and enhancing user experiences when interacting with cloud-based services. From that perspective, client-side software tend to have these benefits:

- Higher fidelity data visualization and interaction models, than the HTML-based minimalist models allowed in browsers 
- More robust client-side state management 
- More smoothly bridge on-line and off-line modes 
- Take advantage of the device's hardware resources and deliver targeted experiences in different form factors 
- Not restricted by the browser's sandbox security model 
- One-time installation cost for all implemented features 
- User experience as a focus; more than accessibility 

Of course, Microsoft has a vested interest in keeping the desktop and client software relevant. But the industry is not oblivious to them too, as many well-known examples exist today:

- Apple iTunes, iPhone SDK 
- Adobe AIR 
- Google Gears, Android, Desktop, Toolbar, Pack, Earth 
- Yahoo Konfabulator 
- eBay Turbo Lister, Outlook AddIn 
- Salesforce Offline and Mobile Editions, Outlook integration 

**Development Concerns**

There are many well-documented issues regarding client software development, that have turned many developers away in the past. However, just as Web application platforms are starting to integrate more with the desktop and client-side deployment models, software client platforms have also integrated many benefits from Web application platforms. For example,

- _Moving programming models to a higher level than the operating system._ The declarative development model for browser-based applications allows developers to work at a much higher abstraction level and not have to worry about infrastructure-level issues. Similarly, client-side platforms like Java SE, .NET, Adobe AIR, Google Gears, etc. also provide sandbox models where developers don't have to be concerned with things such as memory management and garbage collection, system-level security, etc.

- _Web-based software deployment and distribution_. Just like FireFox and Opera, which are client-side software too, client-side platforms today allow distribution via the Web with simple download & install processes, and self-updating capabilities (in terms of versions, patches, updates, etc.).

- _Cross-platform and cross-device application portability_. There is no consistent story from this perspective, but some progress has been made. Off-line RIA platforms such as Google Gears, Adobe AIR, Microsoft Live Mesh, etc. all support Web-based development models and technologies. However, fundamentally, they are still very technically different platforms and require unique developer skillsets and knowledge.

- _Overall complexity_. Similarly, levels of complexity vary greatly between different platforms. However, in general we do see that client-side platforms are also adopting more declarative programming models, like the use of XAML in WPF applications instead of using proprietary/binary controls and manually bind to them. In fact if the level of richness required in an application goes above a certain threshold, adopting client-side platforms may be a simpler approach than trying to do so in Web applications.

**All About User Experience**

Ultimately, browser platforms will continue to serve as the easiest way to enable broad reach and ubiquitous accessibility to a large customer base. But at some point, one of the best ways to differentiate and add value is to improve on user experience.

And it's not limited to desktop client software. Increasingly, and sometimes more appropriately, locally-installed software are being used on mobile devices to deliver more intuitive user experiences. For example, applications on iPhone can be developed using common Web technologies, but they do need to be built on the iPhone SDK in order to integrate seamlessly into the iPhone experience. On the other hand, WAP-based or browser-based mobile applications tend to be ultra-minimalistic and comparatively less intuitive to use.

One of the ways to look at this is to determine whether a particular application adds more value to the user by being client-centric, which cloud-based services become complementing factors; or by being cloud-centric which means client software is best suited for specialized purposes.

Anyway, software clients may not be the default choice in providing cloud-based services to users, but they can be a useful option on any architect's tool belt. They're not always worthwhile, but just as no one technology is one-size-fits-all or all-supplanting, software clients can add significant value under the appropriate circumstances.
