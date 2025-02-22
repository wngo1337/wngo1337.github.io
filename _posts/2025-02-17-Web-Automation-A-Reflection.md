---
layout: post
title: Web Automation - A Reflection
subtitle: Looking Back on My Love For Selenium
cover-img: /assets/img/2024_11_15_post/worryfrog.jpg

thumbnail-img: /assets/img/2024_11_15_post/worryfrog.jpg
share-img: /assets/img/2024_11_15_post/worryfrog.jpg
tags: [ Automation, API, tools ]
---

This is just a quick post on something that popped back into my head a while ago.

It's been a long time since I last wrote an autoplayer. I was always heavily inspired by
neocodex.us, which had a suite of automation programs for the beloved virtual pet site, Neopets. By
the way, that site is literally running on a server out of someone's basement right now, and I
admire the dedication. What does that have to do with me? It's many years later now, and I had the
random thought to go back and reflect on one of my old web projects that was implemented with
Selenium.

To me, it's pretty clear now that the planning phase is one of the most important parts of a
project. Winging it does work, but knowing exactly what your program needs to do, the core
parts of your solution, and the tools that you will use to implement it are really crucial parts
of a project because it's really hard to undo design decisions once the coding has actually started.
The only problem is that there isn't just one solution, and some are better than others. I mean, it
sounds obvious, right? The funny part is that you can cobble together a functional solution that
does its job but pretty clearly is not the optimal one.

In terms of web/browser automation, Selenium was the go-to toolkit back in the day. Now obviously,
I'm not that old to know all the history, but I do know that it now has quite formidable
alternatives in Playwright and Puppeteer. That being said, Selenium is still a great testing tool
and there's nothing wrong with it. Browser automation is great for mimicking user actions. However,
the big question is whether you actually need to be manipulating/testing the UI itself for what you
are trying to accomplish, or if using the underlying API and HTTP requests would be sufficient. Back
in the day, I used to associate web automation with browser automation, and it was a pretty big
mistake since browser automation is only a subset of web automation.

To be fair, a lot of the time, you don't know exactly what query strings or body parameters are for
the API that you are interested in. Sometimes, it is just easier to click the buttons, especially
when the page HTML isn't well-structured, rather than tinkering with a black box API and having to
map out all the possible actions yourself. You get to think of your workflow at the UI level with a
layer of abstraction between yourself and the API. However, that ease of use comes at a cost: the
cost of rendering webpages (and handling the metric ton of ads on each one!), the cost of stability
because of fragile CSS selectors and page structure changes, the cost of error handling and
debugging due to the unreliable nature of page rendering and waits, and so on.

The costs listed above are not trivial. Selectors break, UIs change, and mysterious timing issues
lurk in wait. Sometimes you can't avoid it like when you're working with Javascript-heavy sites, but
definitely ask yourself twice whether you need to be using your favourite browser automation
library, or whether you could get away with web requests and potentially HTML parsing. Looking back
now, I think it's pretty clear why so many programs I used in the past were implemented via requests
rather than a full blown browser instance.

Don't get me wrong. Web requests have their own challenges. Keeping track of cookies, headers,
authentication, handling status codes, and so on, so there's always a trade-off. Maybe you even miss
the visual feedback that a browser provides. This all goes back to the point at the start that there
are different working solutions, and it's easy to both overthink and not think quite long
enough. I'll let you know when I've figured that part out...

Well, I said what I wanted to say, so let me just say one more thing that really surprised me
recently. Did you know that Jetbrains' Webstorm IDE is free (for personal use) now? So is Rider,
and I never thought I'd see the day when a non-VS Code alternative for Dotnet made itself available
like this. Definitely something to check out for current VS Code Dotnet users.
