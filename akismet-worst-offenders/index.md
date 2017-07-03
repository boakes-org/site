---
title: Akismet Worst Offenders Extension
author: ear1grey
description:
post_id: 609
created: 2006/06/04 12:06:54
created_gmt: 2006/06/04 12:06:54
comment_status: closed
post_name: akismet-worst-offenders
status: publish
post_type: post
---

# Akismet Worst Offenders Extension

This last few weeks the site has been very heavily hit by comment spammers hawking their usual reprobate websites and wasting internet bandwidth.

[Akismet](http://akismet.com/) has been doing a sterling job of catching this spam and not one message has made it onto the site (I wrote about [Akismet's effectiveness in the pre-launch testing](akismet) previously).

In the bad old days before Akismet I'd have to go through the "unmoderated comments list" in order to find the occasional real comment amidst all the spam, this is no longer necessary, which is wonderful.  Comment-Spam-Nirvana has not been reached yet, however.

In order to help keep Akismet working well, and also, to ensure that "false positives" do not go unnoticed it is still necessary to trawl through the "spam list" and look for real comments. So although the problem has been turned on it's head, the requirement on the responsible user is still the same.

The latest version of the Akismet plugin (v1.15) makes this "de-spamming" process easier, but it still leaves the poor website owner with the responsibility of looking at every single spam message in case there are any real comments that have been mistakenly marked as spam.

Informing the Akismet server about these false positives is important because it helps improve Akismet's accuracy, which benefits everyone by ensuring fewer false positives - one hand washes the other, so to speak.

![A screengrab showing a list of common spammers.](/pics/2006/worst-offenders/inuse)

So I wrote a small addition to Akismet 1.15 (pictured) that tries to help. It pre-processes the spam comments and identifies the worst offenders in terms of the domain that's being advertised, or (perhaps more usefully) the IP Address of the spamming computer.

It's not uncommon for me to get several hundred spam comments each day, so certain machines and websites are hitting my site many times. What the plugin does is make those worst offenders really obvious, so they can be removed en masse, reducing the ham-hunting to a smaller and more managable task.

This code is now obsolete, but the post remains for reference.

Download it here: ~~[Akismet 1.15 plus Worst Offenders Extension~~
