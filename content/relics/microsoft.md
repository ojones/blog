+++
date = "2009-11-27T19:25:22-08:00"
title = "Microsoft"
menu = "relics"

+++

Circa 2010, like most Microsoft employees, I was a contractor.  Through [Catalysis](https://www.catalysis.com/) I worked on a some high profile projects including the Windows 7 registration page, Office 2010 registration page, and MSN.com tour.  Each of these projects were small in terms of content, but had high taffic functionality.

{{< figure src="/blog/relics/images/office_2010.png" title="Office 2010" >}}
{{< figure src="/blog/relics/images/win7.png" title="Windows 7" >}}

The registration pages required update and insert write access.  To avoid security concerns of SQL injection (cross browser security was big then), we opted for stored procedures.  This allowed us to go heavy on database hardware while maintaining a small frontend with a secure data access layer.  If I could go back in time, I would have implemented a queue and reserved backend resources when traffic was not high.

The frontend challenge was to localize Windows 7 and Office 2010 pages into over 70 languages.  Having a flexible UI to accommodate differing paragraph and input text lengths required lots of manual testing.  Making the localization performant took some time.

The MSN.com tour was a project to promote MSN.com redesign.  Microsoft Window's butterfly was a key part.

{{< figure src="/blog/relics/images/msn.png" title="msn.com (2010)" >}}

We contracted the hard stuff to be done in both Flash and Silverlight.  This way the functionality happened on the client.  I created a wrapper website and we deployed the Flash and Silverlight files to Rackspace.  Back then we used to talk about HTML 5 the way we talk about web assembly today.  It's funny how time change and don't.


