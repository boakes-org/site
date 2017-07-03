---
title: Browser Forensics
author: ear1grey
post_id: 465
created: 2005/09/01 23:04:45
created_gmt: 2005/09/01 23:04:45
comment_status: open
post_name: browser-forensics
status: publish
post_type: post</p>
---

# Browser Forensics

I just read the most wonderful news article ever: it's about Web Browsers, and Forensic Science. It's wonderful for two reasons: it gets the whole "telling a story" thing wrong by totally misinterpreting the status quo and being technically confused, then it gives an example that is so under-inspired that I had to come up with my own story for how it could be used (and I really enjoyed that bit).

### The Opening Gambit

[The article](http://www.zdnet.com/article/alternative-browsers-pose-challenge-for-cybersleuths/) which is featured today on CNET News.com opens thus:

> MONTEREY, Calif.--The advent of Firefox and other alternatives to Internet Explorer means cybercops have to learn new tricks for their investigations.

Given their heritage, describing an "advent" of Firefox or Opera is wholly misleading to readers who do not know the history of the world wide web.  It makes them sound like a newcomers rather than the nth generation of browsers that have both been in constant development for over 10 years.

The "new tricks" that have to be learned are nothing of the sort. Internet Explorer, [Firefox](http://mozilla.org/products/firefox), [Opera](http://www.opera.com) [et](http://en.wikipedia.org/wiki/Lynx_\(browser\)) [al](http://www.apple.com/safari/), are all examples of web browsing software, and the article's introduction implies that Internet Explorer is a standard to which these others should conform - it is not.

IE uses standards (often incorrectly or half-heartedly) to provide access to the World Wide Web, just like its "alternatives". Essentially (for those non technical readers) the whole article's basis can be summed up with the following analogy:

> **Bananas and other fruits are alternatives to Oranges**, and furthermore some people are actually eating these new-fangled Bananas! What are we going to do? Everyone knows Oranges can have their pips removed using a juice extractor, but Bananas don't have pips. Whatever you do next, don't panic!

### Describing the Problem

The reason that this is a problem for "forensic investigators" is described as follows:

> **Internet Explorer hides nothing from police** and other investigators who examine PCs to discover which sites the user has visited. They know the location of the IE browser cache, cookie files and history, and they know how to read those files. Also, popular forensics tools can help out.

This is flawed logic. If the investigators don't know where something is, then that does not mean it is hidden. The process of finding this information is called "forensic investigation", not "McForensic Harvesting". I also note that if "popular" forensics tools can't handle all browsers, they're not going to be popular for very long (apart from among criminals).

### Catchy Monkey

The article then goes on to identify an intricacy of IE that may be used to prove that a URL was manually entered rather than just being a link that was clicked on by the user. This really _could_ be used to convict someone, but it's more likely to happen at the pivotal moment in a Hollywood blockbuster movie, where all appears lost: as the the clock ticks down the young misunderstood toothy geek who has previously appeared socially mal-adjusted removes her* glasses, shakes down her hair, somehow transforms into a beauty on the edge of adulthood, who appears on the stand as an expert witness and foils the crime syndicate. The film closes with a ticker-tape parade.

What the article fails to point out is that IE is more full of security holes than a prison made of edam that's fallen victim to a surprisingly large and hungry family of mice. This insecurity makes it particularly easy for evidence collected from an IE user's machine to be brought into doubt because it is remarkably easy to show that it could quite easily have been tampered with by a third party.

So that's plus-one point for forensic simplicity, but minus-infinity for the admissibility of evidence.

[*]: You were thinking geek = male right?
