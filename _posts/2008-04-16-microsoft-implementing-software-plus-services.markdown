---
layout: post
title:  "Microsoft Implementing Software Plus Services"
date:   2008-04-16 12:00:00 -0700
---

Microsoft has been talking about "Software + Services" (S+S) as its vision of the future for a while now (see related posts on S+S: Microsoft Platform Overview & Talking about Software Plus Services). People like Bill Gates and Ray Ozzie often talk about the applicable patterns and trends that exemplify this concept, even though they don't always mention the moniker.
And Microsoft's execution on this direction is quite visible too. From continued investments on the desktop and enterprise software, to the latest and still growing cloud platform that brings many of the traditional capabilities into the Web.

![Microsoft Services Platform](/assets/20080416-2416532401_bb76dc0fc9.jpg)

For example, many of the enterprise servers - Exchange, SharePoint, Office Communications, and eventually Biztalk and SQL Server as well, are all being implemented as services in the cloud that users can use directly, without investing in their own physical infrastructures to host and manage them. There are also a lot of progress being made in the consumer space in the form of Windows Live services.

However, a major value proposition in S+S is the ability to integrate traditional software with distributed services, and bring the best of both worlds together. What has Microsoft done so far to implement that S+S vision?

Basically, many efforts are happening across the board. Some of the more visible ones include:

**Exchange** - it supports multiple delivery means (hosted on-premise, outsourced hosting/management by a partner, and cloud-based service from Microsoft), it supports many clients (Outlook, OWA, Outlook Mobile, Outlook Voice Access), multiple licensing models - traditional perpetual and subscription; plus itself can be a consumer of attached services such as Forefront spam/filtering services

![Exchange](/assets/20080416-2416532333_bd18092d7a.jpg)
 
**Office System** - Office clients combined with SharePoint server represents a business productivity platform (client-server interaction and leveraging the many valuable enterprise services in SharePoint such as enterprise search, content management, business data catalog, business intelligence, etc.). Excel spreadsheets can be published into SharePoint and then provisioned as web services, InfoPath forms, stored as part of SharePoint’s InfoPath services, can be rendered on InfoPath clients but can also be rendered directly from SharePoint as forms services. Office clients themselves can also be extended with .NET to connect to back-end systems whether directly or via SharePoint or Biztalk. For example, Office Live Workspaces which is a cloud-based SharePoint service for consumers, SharePoint Online for businesses, etc. 

![Microsoft Office System](/assets/20080416-2420757884_d85eaf3302.jpg)

**SharePoint** - SharePoint Server itself can be deployed on-premise, outsourced hosting, or accessed as a subscription service from Microsoft (SharePoint Online). It also has many other flavors such as Office Live, Office Live Workspaces that live in the cloud as services for consumers to use 

**Windows Live** - known as a set of cloud-based services, but Microsoft has also delivered a set of client-side software (Mail, Messenger, PhotoGallery, Toolbar, Writer) to improve the user experience, in addition to the browser-based interfaces. Also many of the services offer API’s for people to build applications with.

![Windows Live Services](/assets/20080416-2419943513_881ec1f23a.jpg)

**Office Communications Server** - similar to Exchange, it now also has a cloud-based service for people to use (Office Communications Online), plus API's for developers to build specific branding and user experiences

**Duet** - a product that integrates Microsoft Office with SAP. Basically users can use the Office clients as the UI to SAP services 

**Xbox** - Xbox Live is one of the first examples of S+S 

**Dynamics** - similar model to Exchange - multiple deployment/delivery models, licensing models, and client access channels 

**Windows** - Windows Update is a componentized client and cloud-based service interaction model; similar is OneCare 

These examples all demonstrate the fundamental principles of S+S:

![Software plus Service](/assets/20080416-2416584091_69c60b9e65.jpg)

One recent offering that is particularly interesting, is [Windows Live Workspaces](http://workspace.officelive.com). This service offering, in a way, is Microsoft's response to Google Apps. Instead of converting the Office client software suite (Outlook, Word, Excel, PowerPoint, Groove, OneNote, Visio, InfoPath, Access, etc.) into browser-based solutions to compete head-on with Google Apps, Windows Live Workspaces was delivered to offer the sharing and collaborating capabilities that have been cited as the biggest shortcoming when using the Office clients.

Now Microsoft actually has been delivering SharePoint services for a number of years now to provide that file sharing and collaboration scenarios for workgroups and enterprises. But there was a gap for consumers and inter-organizational scenarios that traditional SharePoint deployments (inside the firewalls) don't address very well.

Thus Windows Live Workspaces is still built on SharePoint, but has been designed specifically to support consumer and end-user collaboration. It provides capabilities for fine-grained document-level access control, ubiquitous access, cloud-based storage, and client-side add-on's that integrate directly into the Office clients. So users can create/open/save documents into Windows Live Workspace directly from Word or Excel, for example. And of course, user always have the option to save documents locally until they're ready to share with other people.

This approach illustrates the S+S approach by leveraging best of both worlds. Rich client-side software (criticized as bloatware sometimes but it can also be perceived as having the capabilities ready-to-use regardless of where a user is; having internet access or not) that fully leverages the power of the client device platform to maximize individual productivity, while leveraging cloud-based platforms for sharing and collaborating with others to maximize group productivity.

(originally published at <https://blogs.msdn.microsoft.com/dachou/2008/04/15/microsoft-implementing-software-plus-services/>)
