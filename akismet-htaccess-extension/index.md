---
title: Akismet htaccess extension
author: ear1grey
description:
post_id: 612
created: 2006/06/08 16:57:57
created_gmt: 2006/06/08 16:57:57
comment_status: closed
post_name: akismet-htaccess-extension
status: publish
post_type: post
---

# Akismet htaccess extension

My spam counter in Akismet has been steadily rising of late, and it's been approaching 10,000 caught spams very quickly. Yesterday it went through 9,950 and with my average of over 100 spams per day it should have gone through the 10,000 barrier by now. But instead I've had about 3 spams today. Did I just find an off button for spam?

## Worst Offenders

I wrote the other day about [a small Akismet extension](http://boakes.org/akismet-worst-offenders) that I'd been playing with that helps remove the worst offenders from the list of caught spam - this in turn makes false positives easier to recognize. One of the things that the extension notices is which IP addresses are particularly prolific, it's this information that helped me to a 95% (and rising) reduction in the spam that I send to Akismet to be checked.

## htaccess

When writing about the extension on the Akismet mailing list, I suggested that hooking the worst offenders IP list apache htaccess file should provide a simple dynamic means of rejecting spams before the http request has been processed by the server (and before the akismet plugin has had to check it against it's server). So I tried it, and it works, _apparently_ flawlessly so far. In my access log I can see that over 100 requests have been rejected so far today. That's 100 requests that are not sat in my "spambox" waiting for me to check for false positives. Todays Akismet spam count is in the single figures, instead of the triple figures. Fantastic.

## Ongoing Thoughts

So what does this mean for this site?

1.  If a spammer does manage to leave a message here, then it's caught by Akismet and marked as such, it never gets through.
2.  When I remove those messages, I can optionally ban the IP address from whence they came.
3.  Bandwidth usage is reduced becuse the server does not accept connections from spammers, and fewer two way chats with the Aksimet server are necessary.
4.  The comment database does not get needlessly filled with temporary comments that are removed once their spammyness has been identified, so the DB and DB indexer has less work to do. So what does this mean for the Akismet project?
5.  There will be fewer hits from this site, so more time to concentrate on others.
6.  If the changes can be used by others, the net effect will be a more scalable and responsive service.
7.  If large scale uptake was achieved, the spam zeitgeist might start to look different because the number of spams being checked daily should significantly reduce. There are several obstacles to global spam nirvana, including:
8.  The installation proecess will require a tiny bit of "hand cranking" to ensure the htaccess file is in a suitable state for automatic updating.
9.  The system should probably exist as a separate plugin that hooks into the Akismet plugin at appropriate points, but those points haven't been defined yet.
10.  The system should probably exist as a separate plugin that hooks into the Akismet plugin at appropriate points, but those points haven't been defined yet.
11.  Not everyone uses Apache, so not everyone has an htaccess file.
12.  Not everyone uses Wordpress, so Akismet service users on other platforms will have to re-implement the idea.

## Download

Note: this is an _experimental_ extension to Akismet. It _appears to work_ for me, and I will be _delighted_ if others try it an can give useful feedback for the experiment.

**Pro's and PHP/Apache black-belts only at the moment.**

i.e. Please don't ask linux/htaccess questions - I'd love to help, but I don't currently have time to hand-hold on a non-production experiment.

Still keen? Great. If you're really brave and want to try it out, you need to carefully follow these steps.

1.  Precondition: Follow the installation instructions for [Akismet](http://akismet.com) and ensure it's working correctly.
2.  Download the [Extended Akismet Plugin](http://boakes.org/download/akismet-1.15-wo-hta-tpfix.zip).
3.  Replace the akismet plugin with the one you just downloaded - it should pick up all the configuration from the "official" version of the plugin.
4.  In the WP admin interface Open the "Manage | Files" tab, and check that your htaccess file is writable.
5.  The automatic IP banning is written between two markers that are "# BEGIN worst-offenders" and "# END worst-offenders". If you already have a deny list in your htaccess file, just add the markers to the list. Mine looks like this:

```
    Order Allow,Deny

    # BEGIN worst-offenders

    Deny from 202.75.49.130 Deny from 202.75.49.131 Deny from 202.75.49.133 Deny from 202.75.49.134

    # END worst-offenders

    Allow from all
```

6.  From now, when you look at your "Worst Offenders" list in Akismet, you should see the option to ban the spamming IP addresses when you delete the messages.

7.  Feedback and ask questions below

### FAQ

1.  Is this a polished and buffed plugin that is ready for the prime time?

 **No! Absolutely not!** For many reasons. This is _an experiment_ to see if the idea works and to generate some discussion around what's needed for dynamic spam blocking systems to work. Its public so that those with the right skills can try it, or examine it, and perhaps learn from or contribute to it. If you're an armchair amateur blogger, this plugin is not for you; yet.
2.  Why are some items in the list of offenders not ticked?

 Items with fewer than 4 spam messages are not ticked - this is flexible within the plugin, but not yet configurable.
3.  Why do I only see 10 "Worst Offenders" at once?

 Items with fewer than 4 spam messages are not ticked - this is flexible within the plugin, but not yet configurable.
4.  I have an idea for making this better, what should can I do?

  Discuss it, implement it, share it.
5.  Does all this IP address checking add more load onto my poor server?

  The benefits far outweigh the costs. It is a small increase at the front end, but a massive decrease overall. Comparing an IP address is mathematically simple task, so it is very fast. Storing the comment, sending it to the Akismet service and then removing it from the database is much more work.
6.  Could this be an end to spam?

  No. The number of zombie machines out there is too large to block them all, this method reduces spam from zombies that know about your website, so it directly saves your resources whilst reducing the number of calls your server makes to the Akismet service.

7.  How many machines can this method block?

  Currently IP addresses drop off the end of the list after 400 are added, so the least recent disappear. This is adjustable in the software but not user-configurable yet.

8.  If I am blocking spam at source, will capability of Akismet be diminished, because it might not see new variants of spam as they emerge?

  I don't know. I doubt it. Maybe Matt can add detail without giving too much away.
