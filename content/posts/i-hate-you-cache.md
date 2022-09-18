---
title: "Working with caches you can't control"
date: 2013-01-15
---

Recently, I worked on a project where the client controlled their production environment.  They're using EdgeCast and we didn't have access to force a cache clear when deploying new releases to production. So we'd push, ask them to clear cache, and wait as many as 8 - 10 hours to make sure everything was working fine.  This sucks, but what I didn't expect was that even after they cleared the cache, old files were still being served. So we'd ask for another cache clear, and wait. This was as painful as it sounds.  

Eventually, they asked us to simply put no-cache headers on all of our files. This kind of defeats the purpose of even having a CDN, but okay.  We tried that next.  However, even with cache-control headers in place, the CDN would unpredictably serve older versions of .js and .css files.  There was a lot of back and forth and finger pointing about who's fault it *really* was that prior-release .js was still being delivered.  They finally suggested that we rename our asset files with each release.  This *also* sucks, but was at least a solution that we could control.  With this script as part of our build, we met them halfway and sort of renamed asset files with each release.  

[Here's the repo](https://github.com/drnikki/cli-cachebuster) for the super simple script should you ever find yourself in such a position.



