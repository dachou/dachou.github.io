---
layout: post
title:  "Silverlight and Live Messenger at Photobucket"
date:   2009-07-13 12:00:00 -0700
---

Photobucket has collaborated with Microsoft to build Photobucket Visual Search (<http://photobucket.com/visualsearch>), making use of Silverlight, Windows Live Services and Photobucket's Open API platform. Photobucket Visual Search uses Silverlight to provide a rich and entertaining search experience, by displaying photos and videos in an easy-to-browse interface. The experience shows up search results, as well as related terms, helping users to find images they might not have in the past.

Recognizing that photos are about sharing a social experience, Photobucket decided to use Microsoft's new Windows Live Messenger Web Toolkit to socially enable this Visual Search experience. Windows Live Messenger has over 320 Million active users, with over 32 billion social relationships between them. Sharing an image with friends on Windows Live is as easy as a click of a button with Photobucket Visual Search.
 
![Photobucket Visual Search](/assets/20090713-image_4.png)

## Situation

Photobucket is a very popular site on the Internet for uploading, sharing, linking and finding photos, videos and graphics. Photobucket is usually used for personal photographic albums, remote storage of avatars displayed on internet forums, and storage of videos. Photobucket's image hosting is often used for eBay, MySpace (now a corporate cousin), Bebo, Neopets and Facebook accounts, LiveJournals or other blogs, and message boards. Users may keep their albums private, allow password-protected guest access, or open them to the public.

Below are some statistics (circa 2007) regarding the Photobucket.com website.
- 30+ million searches processed / day 
- 25 million unique site visitors/month in the US, and over 46 Million unique site visitors/month worldwide 
- Over 7 billion images uploaded 
- #31 in Top 50 Sites in the US 
- #41 top 100 Global Sites 
- 18th Largest Ad supported site in the US 
- 41.4% share of U.S. visits to photography web sites 
- 56% of users are under 35, and 52% are female 

This project is intended to enhance Photobucket’s user experience while mapping specific objectives to the following core business goals:
- Leverage rich software to create a fun and engaging experience 
- Social communication features that provide increased web traffic 
- Encourage users to add their own tags and collect metadata in the process 
- Improve user acquisition and retention to the Photobucket website 

Richer visualization and interaction, plus social networking capabilities, were chosen as the means to achieve the goals of improving user acquisition and retention. Consequently, Silverlight and Windows Live Messenger Web Toolkit were chosen as the components from the Microsoft platform that can be leveraged for the Photobucket Visual Search project. Photobucket’s existing open API’s (HTTP/REST-based) are used directly to support the search client application.

## Architecture

The project architecture consists of Photobucket’s existing server infrastructure, which provides the open REST-based API’s, images, albums, thumbnails, groups (featured, most active, most recent, most contributions, contests, etc.), static content, etc. The Photobucket.com website itself is a user interaction/presentation layer on top of the thousands of servers deployed as part of the content infrastructure. The Photobucket.com website manages all the metadata associated with the massive amount of content, such as tags, descriptions, comments, image ownerships and relationships, user memberships, etc. Searches done on the Photobucket website is performed on the metadata and indexes; and the search results point to actual locations of content and assets across the massively parallel content infrastructure.

The content infrastructure consists of multiple farms of thousands of servers, each manages different types of content, with user data partitioned horizontally across servers in each group. The content servers can be accessed directly using sub-domains on photobucket.com, such as i98.photobucket.com for one of the image clusters, t104.photobucket.com for one of the thumbnail clusters.

Application requests are managed by the photobucket.com website, and the open API’s are managed via api.photobucket.com servers. Search queries retrieve an XML response, which represent search hits, with associated metadata, and actual image locations potentially pointing to hundreds of different servers where they physically reside.

The Silverlight search client implementation is designed to fully leverage the search service as part of Photobucket.com’s open API’s. It captures the search queries from the user, then sends it to api.photobucket.com for processing, then interprets the returned XML, renders the result, and downloads individual thumbnails from actual server locations in the thumbnails server farm.

The Windows Live Messenger Web Toolkit implementation is mostly client-side. Photobucket hosts some of the files such as static images for branding the messenger interface, but most of the files are retrieved directly from the messenger service in the Live Services platform. Integration with the Silverlight Visual Search application is done through the JavaScript bridge.

A diagram representing the logical architecture is shown below.

![architecture](/assets/20090713-architecture.png)

The overall end-to-end architecture consists of these components
- **Client** – Silverlight 2, Windows Live Messenger Web Toolkit, JavaScript, CSS, HTML, etc. 
- **Server** (Photobucket) – Linux, Apache 2.2.4 (EL4), PHP 5.2.6, MySql 
- **Server** (Live Services) – IIS 6, ASP.NET 2.0.50727 
- **Tools** – Visual Studio 2008, Expression Studio 

## Silverlight Visual Search Development

The default target dimensions for the application are 1024 X 768. However, the application supports browser resizing and will adjust accordingly when the user changes browser window size dynamically.

The application has two primary states:

- **Main View** (Search & Explore) – This is the state the user will be in initially and for a majority of the search and explore functionality. The main view displays thumbnails of the image results. It also allows users to modify their searches, or explore further using alternative searches. 
- **Zoom View** – The secondary state of the application brings the user into a view where the focus is on the viewing aspect of the large image and the image options, including sharing with Live Services. 

The project team went through many data visualization designs for the search results. In the end, a simplistic one that represented a similar model to the rest of the Photobucket site was chosen.

## Windows Live Messenger Web Toolkit Integration

While in Zoom View, a user can share the photo via IM using Live Messenger. Doing so will prompt the user to sign in or register to sign up for Live Messenger. If the user is already signed in, this will trigger the user's Windows Live contact list to pop up.

### Delegated Authentication

Signing in will link a user’s Windows Live ID with the Photobucket.com website, granting an authentication consent (as a site-wide stored consent token) to Photobucket so that web pages generated from Photobucket can reuse this session with Live Messenger, and not have to require the user to sign-in on each page.

The project team decided to leverage Live Messenger’s Delegated Authentication method because it provides the most unobtrusive method to the existing Photobucket’s membership system, as well as simplicity in implementation as the identity federation approach would be significantly more complex.

### Messenger Web Bar

The Messenger Web Bar is a single UI Control that contains a full Windows Live Messenger experience. The Messenger Web Bar has the following functionality:
- **Contact list** — The contact list enables the user to manage contacts and interact with them. 
- **Conversation list** — The conversation list contains all active conversations. 
- **User area** — The user area shows the user's presence and enables the user to update this information 
- **Cross-page navigation** — Cross-page navigation enables the user to stay signed in to Live Messenger while navigating from page to page within your application Web site. 

This functionality is encapsulated within a small bar at the bottom of the page. Because the Live Messenger Web Bar works across pages, conversations that start on a page on the application Web site can continue on another page of the application Web site. This functionality enables an application Web site to use the Live Messenger Web Bar as a platform to deeply integrate Live Messenger functionality and data into the site. Making an application Web site more social with the Messenger Web Bar and UI Controls can significantly increase user engagement.

Shown below is a picture of the Messenger Web Bar used as part of the Visual Search experience.
 
![Photobucket Visual Search](/assets/20090713-image_6.png)

Once the user is logged into the Windows Live Messenger service, the user can view and interact with the list of contacts managed in the Windows Live service. The user can see also see presence information in terms of who among the contacts is online or offline at the moment. An IM conversation can then be initiated just by selecting a contact. If the user initiates an IM conversation while in Zoom View, Visual Search will automatically insert a link that says “Check this photo” with a URL to the actual image.

## Application Scenario

This project demonstrated how Silverlight can be leveraged to add value to a website completely built on the LAMP stack. It also showed how Live Services can be leveraged, without any significant custom development effort, to add social computing capabilities to any website. The combination of rich clients, and composition of multiple cloud-based services on the Web, represents a Software Plus Services implementation approach, and how it enhances existing Web browsing models and improves user acquisition and retention.

(originally published at <https://blogs.msdn.microsoft.com/dachou/2009/07/13/silverlight-and-live-messenger-at-photobucket/>)