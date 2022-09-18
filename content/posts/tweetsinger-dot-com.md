---
title: "TweetSinger.com"
date: 2012-09-22
---

We (LBi US, where I’m a developer) just launched TweetSinger.com, a Sony
Mobile campaign site for their new Xperia series phones. This was my
first large non-Drupal project in a while and it was fun to get to do
something different.

What was initially presented to me as a “quick two-page site” took a
month of long hours to finish.


**The technology:**

It's built in Symfony, backed by MongoDB, and using HTML5 canvas for
visualizations.

We’re running a ton of Ubuntu web servers behind a load balancer and one
MongoDB server all on Amazon EC2. I got to do all of my own devops on
this project and it was nice to have complete control of the stack. We
deploy with Capistrano (and its multi-stage extension) and files are
stored on S3. Integrating with S3 was totally painless using a
pre-existing Symfony library. It was an 11th-hour switch due to storage
concerns with EBS and it was absolutely the best choice we could have
made.

I was initially concerned about storing huge json files in the db (each
record is about 1MB), but it hasn’t been a problem at all. This is a
fairly simple application for a database - there won’t ever be race
conditions. The record is written only once upon song creation and will
only be read thereafter. (A few edge cases notwithstanding). Getting the
mongo server & RAID’ed EBS volumes was a lot easier than I expected.

The conversion is being done by a REST server that was written in Java,
lives in Tomcat, and is built with ant via the the same Capistrano
script I use to deploy the site.

**Lessons learned:**

An Amazon EC2 instance instance has to be off to make an image of it. This
is one of those things that sounds so obvious, until you forget to shut
an instance down before making an AMI and then can’t figure out why you
can’t SSH into it.

The site itself is fairly small - only two discrete pages and a minimal
admin area. It was initially presented to me as “a quick little build.”
It’s easy to fall into the trap of thinking that perhaps some of the
best practices that are part of developing large websites wouldn’t be
needed on a smaller project. This, of course, is wrong. Best practices
exist usually because they’re “best.” Not best “only if your dev team
has 15 people on it.” Or best “just when you’ve got plenty of time.”

Having a structured build system, using pull requests to get code into
master, documenting everything in a place any team member can access -
these practices saved us hours even on this “little” website. I only
briefly considered sidestepping some of these, but those practices are
there to protect me (and the code) from myself as well.

The super-smart Yury Tillis was the front-end engineer on the project
and is supposed to do a write-up of some of the magic he worked for the
visualization.

Congratulations to the entire LBi US team who worked so hard to get it
launched.

Check it out at [www.tweetsinger.com][]

  [www.tweetsinger.com]: http://www.tweetsinger.com
