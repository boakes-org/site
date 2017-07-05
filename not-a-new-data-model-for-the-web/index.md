---
title: Not a new data model for the web
author: ear1grey
post_id: 355
created: 2005/07/27 11:15:41
created_gmt: 2005/07/27 11:15:41
comment_status: open
post_name: not-a-new-data-model-for-the-web
status: publish
post_type: post
---

# Not a new data model for the web

[tl;dr] A slashdot [article](http://developers.slashdot.org/article.pl?sid=05/07/27/0152211&tid=221&tid=8) hails a seminal lecture and labels the sementic web a failure.  In fact, AB gave an interesting presentation about a solution to a rather specific but common problem, that appears to make the importance of the semantic web more obvious to Average Joe.

I think the [recent presentation](http://www.itconversations.com/shows/detail571.html) by Adam Bosworth at the MySQL User's Conference has been a little over-interpreted. It's certainly interesting and presents some useful perspectives, but it's not the "seminal lecture" that [today's slashdot story](http://developers.slashdot.org/article.pl?sid=05/07/27/0152211&tid=221&tid=8) describes.

AB begins by introducing his preference for simplicity, and what he calls _the virtues of dumbness_, he suggests that because complex things break, and simple things work, simple things are better, and highlights that his employer, Google, has the dumbest [query language](http://www.google.co.uk/help/features.html) in the world, but because it's simple, it works.

Anybody that's studied the underlying scientific concepts of [Information Retrieval](http://en.wikipedia.org/wiki/Information_retrieval) will know that the Google search interface example is a gross simplification of what's happening under the surface. AB has blurred the distinction between the usability of the interface and the underlying capabilities of the system for the sake of fitting his talk within the time available.

Based on the simplicity premise, the concept of a low-tech query language for web data is introduced: a language so simple that average programmers and content developers can understand and work with it; a language that doesn't query data tables, but which queries data that's on the web.

> "To do this needs an open format for data. It has to be one grammar or the engine will have a hard time. It has to be sloppy or Average Joe won't be able to use it."

The most suitable target use for this query language appears to be the data aggregator; i.e. it's not a detailed data model, it's a a query protocol that can encapsulate diverse result sets, so it's potentially very useful for agent-based computing, but unlikely to be "the new data model for the web" that the slashdot article portends. Importantly, although querying web pages is what's being discussed, the issue of the semantic web is sidestepped:

> "this is not the semantic web. I don't understand top down ontologies. The semantic problem is still yours [so] you have to figure out what [the result data] means."

So, AB is suggesting a simple query language, not a description of how the queries should be fulfilled on the server end (which will require semantically enhanced databases in many cases) or how the results can be interpreted, which will need semantic inference, which again needs semantic markup, so [RDF](http://www.w3.org/RDF/) seems a key supporting technology.

In the questions at the end, AB confirms that RDF (and by proxy the [semantic web](http://www.w3.org/2001/sw/)) is not what he's talking about, suggesting that it has empirically failed his simplicity test, because people get confused about arcs, nodes, verbs and rdf grammar. Of course, this isn't empirical testing at all, it's conjecture based on his admitted confusion (and a confusion I can empathise strongly with on occasion, having grappled with RDF constantly for the last few years), but just as most of us speak languages without understanding the intricacies of their grammer, so it will also be true that most of us will be able to use RDF and other semantic tools once their libraries and concepts mature.
