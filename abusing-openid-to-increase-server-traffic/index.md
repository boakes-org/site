---
title: Abusing OpenID to Increase Server Traffic
author: ear1grey
description:
post_id: 1180
created: 2009/08/20 19:27:05
created_gmt: 2009/08/20 19:27:05
comment_status: open
post_name: abusing-openid-to-increase-server-traffic
status: publish
post_type: post
---
# Abusing OpenID to Increase Server Traffic

Whilst idly watching my syslog recently (as one does), I noticed with some discomfort, that outbound connections were being made from my server, to sites of questionable repute. Something that might indicate that the machine had in some way been compromised. The logs show messages such as:

```shell
Aug 20 14:40:20 hostname apache2: Successfully fetched 'http://litjnz.cn/': GET response code 200
Aug 20 14:52:35 hostname apache2: Successfully fetched 'http://tqeetazx.cn/': GET response code 200
Aug 20 15:00:26 hostname apache2: Successfully fetched 'http://cnduiz.cn/': GET response code 200

Aug 20 12:13:54 hostname apache2: CURL error (6): Couldn't resolve host 'byuxlcifxlso.com'
Aug 20 17:24:43 hostname apache2: CURL error (7): couldn't connect to host
Aug 20 17:24:58 hostname apache2: CURL error (28): connect() timed out!
Aug 20 17:25:07 hostname apache2: CURL error (28): Connection time-out
```

After a little investigation, checking various access logs and processes, and comparing several different logs at once for serendipitous links*, I spotted, with some relief, that my server hadn't been compromised after all.  It was, in fact, the <a href="http://openid.net/">OpenID</a> service that I run from my server, that allows others to login to this site without registering here.

So, any OpenID server can be <em>forced</em> to make a connection to a third party server, and make a page request. This means that (for example) rather than requiring 1000 distributed bots in order to generate network traffic to a server from 1000 locations, all that is required is one bot and a list of 1000 OpenID servers.

Such a tactic is useful for black-hat SEO companies, for example, who want to appear to prove that whatever secret magic tactics they're using to increase traffic are working. Whilst this form of traffic generation is cute, there is perhaps a more interesting angle.  With thousands of OpenID services around already, and hundreds, if not thousands more being added every day, OpenID might become the platform of choice for proxying and amplifying a <a href="http://en.wikipedia.org/wiki/Ddos#Distributed_attack">DDOS</a> attack.

OpenID server software needs to be able to detect and prevent this kind of attack, or the server on which it's installed is likely to become very unpopular, very quickly. 
