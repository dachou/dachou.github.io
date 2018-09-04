---
layout: post
title:  "LineRider with Silverlight and Windows Live Services"
date:   2008-07-11 12:00:00 -0700
---
(originally published at [https://blogs.msdn.microsoft.com/dachou/2008/07/11/linerider-with-silverlight-2-and-windows-live-services/](https://blogs.msdn.microsoft.com/dachou/2008/07/11/linerider-with-silverlight-2-and-windows-live-services/))

Last week InXile Entertainment launched a new version of the [LineRider](http://www.linerider.com/) game, built using Silverlight 2, and integrated Windows Live services (ID and Messenger). This is one of the projects me and my Microsoft team were directly involved with, by partnering with InXile Entertainment and Cynergy Systems. And we are quite excited with the results.

The original version of Line Rider, launched September 2006, is a Flash-based game that has been cited by a number of publications (i.e., New York Times, Wall Street Journal, Time, CNET, GameZone, etc.), and was one of Yahoo’s top 10 search words in late 2006. Existing momentum includes over 36,000 videos posted on Youtube (with more than 5 million views), ~10 million page views per month with ~1.7 million unique visitors.

With this release, [we ported the Flash-based version to Silverlight](http://linerider.com/en/news/inxile-entertainment-move-free-web-version-line-rider%E2%84%A2-adobe-flash-microsoft-silverlight).

We used Expression Blend to create the game layout and controls, used Visual Studio 2008 and C# for the game logic and physics engine implementation, and built on top of the Silverlight 2 beta 2 SDK.

So what's the big deal? Take a look at this video of one of the sample games.

<iframe width="679" height="545" src="https://www.youtube.com/embed/bcu8ZdJ2dQo" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>

Loved the snappy Cowboy Bebop music theme they used in this video. More amazing video clips available on Youtube.

Basically, users draw lines that make up the tracks, and little Line Rider bobsleds through the tracks as driven by gravity (while holding on for dear life). Very simple game mechanics, but quite an addictive cycle drainer if you get into it. 🙂 There is already a large volume of video content showing all kinds of complex and intricate designs created by the existing community.

**Flash to Silverlight**

So why did we convert from Flash to Silverlight? Undoubtedly the change introduced inconveniences for existing users, plus the perceptions brought along by Microsoft's reputation (good and bad).

Now I have a tremendous amount of respect for Flash and the community it has generated. There are some pretty impressive applications built on Flash today, and the rich ecosystem consisting both proprietary and open-source tools and solutions. And based on my understanding, most things done on either Silverlight or Flash, can also be accomplished on the other platform today.

Of course, we tend to think that leveraging the .NET development platform provides a level of productivity improvement and sophistication, but it really wasn't about the technical merits of either Silverlight or Flash platforms. We were just there at the right place and the right time, and provided an effective partnership to help ensure project success.

At the time, InXile Entertainment was looking for ways to enhance the existing experience and bring it up a level. Specifically, to be able to share more effectively, integrate social aspects, and to be able to create a community around Line Rider. The previous Flash-based version provided excellent single-player experiences. But to share the tracks (i.e., to show others the masterpieces one has created), users resorted to their own means such as using their own video-capture software, media editing software, video hosting service, and had to find online storage or email Flash-based SOL binary files directly to each other, etc.

Thus we worked to tackle these needs for the Silverlight-based version. A couple of major things we did that added value to the project:

- Saving tracks in XML format instead of the Flash-based binary SOL format. This allows for simpler cloud-based storage and sharing, plus eventual cross-platform porting of tracks (with the upcoming console-based versions)
- Integrating Live Messenger and Live ID as part of the authoring and playback environment, which is intended to add a level of social interaction between users
- Associating tracks with music playback to provide an experience similar to video capture/playback when shared

Basically, the intention is to make it easier for users to share and build a more integrated community.

Again, these can be done on Flash too, but we added the partnership to make sure that the resulting product met InXile's expectations. Plus from a long-term planning perspective, we felt that investing on the Microsoft platform has value beyond just the Web-based RIA platform aspect. The .NET skillsets can be reused to build and integrate cloud-based services, expand the community and social aspects, as well as reaching connected device platforms, for next-generation experiences.

**What's Next?**

InXile is working on console-based versions of the game (Xbox 360, Wii, PS3, Nintendo DS, Windows Mobile), called "Line Rider 2 Unbound", which at the moment looks just amazing. Take a look at these videos ([part 1](https://www.youtube.com/watch?v=HQsTXYr5eoM), [part 2](http://linerider.com/en/movie/341646), [part 3](http://linerider.com/en/movie/378497)) for a quick preview of the enhancements they're making to the game.

Looking forward to, at some point, work with these guys again to port the Web-based Silverlight version to include the new Line Rider 2 features.

**About InXile Entertainment**

Located in Newport Beach, California, inXile entertainment is a game development company that focuses on both licensed and original intellectual properties. Formed in late 2002, inXile entertainment develops for personal computers and the major console platforms including the Nintendo Wii, Nintendo DS, Playstation 3, and Xbox 360. Their products include The Bard's Tale and Line Rider.

Read InXile Entertainment's [press release](http://linerider.com/en/news/inxile-entertainment-move-free-web-version-line-rider%E2%84%A2-adobe-flash-microsoft-silverlight) regarding this project.

**About Cynergy Systems**

Cynergy is a leader in the design and development of Rich Internet Applications (RIA) specializing in Microsoft Silverlight and WPF as well as Adobe Flex and AIR. 
Cynergy is privately held and headquartered in Washington, D.C.; the Company's U.S. field operations include Rochester, N.Y., Grand Rapids, Mich., and San Diego, Calif. Cynergy's European operation is based in London, United Kingdom and Copenhagen, Denmark and its Asia Pacific operations are located in Taipei, Taiwan and Sydney, Australia.

Read Cynergy's [press release](http://www.cynergysystems.com/news/linerider.jsp) regarding this project.
