---
layout: post
title: "Getting Skype History"
date: 2012-10-24 16:03
comments: true
categories: [sqlite3, skype]
---

I hate Skype, but I'm stuck using it.  Part of my problem with it is that logs get very large very quickly and going back to find something you forgot to write down (like a server addres) takes forever.  

The solution?  Export your skype logs to something grep-able! (Duh.)  

{% gist 3947360 %}

So hot, so easy, put it in cron and run it all the time.

p.s. Install OSX Developer Tools if you're on a OSX.

p.p.s I totally stole this from a Stack Overflow post a while ago.  If I find it, I'll include the link.
