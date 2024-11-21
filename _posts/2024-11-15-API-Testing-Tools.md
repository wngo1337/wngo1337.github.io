---
layout: post
title: API Testing Tools
subtitle: What's Cool These Days?
cover-img: /assets/img/2024_11_15_post/worryfrog.jpg

thumbnail-img: /assets/img/2024_11_15_post/worryfrog.jpg
share-img: /assets/img/2024_11_15_post/worryfrog.jpg
tags: [API, Testing, Tools]
---

I should probably clarify that I mean manual testing tools in this post. If you
have the time and believe that you need the automation and extensibility that
comes with setting up an API testing framework in your favourite programming
language, then you're probably already happily using it. It might be overkill
depending on which stage of development you are at though. So, with that in
mind, let's continue.

## Read This If You Don't Plan to Read the Post

I use [Bruno](https://www.usebruno.com/downloads) for creating saveable and
structured collections of requests. It is open source and has a very capable
free version that will satisfy the majority of your API testing needs without
forcing you to sync all your data to a proprietary cloud.

httpie CLI is what I use for testing on the fly. It's an alternative to cURL
really. It might feel a bit clunky having to learn the new flags and syntax at
first, but you will quickly learn to appreciate the additional features that it
brings to the table like formatting, coloured output, and really nice JSON data
support. How much you will like it depends on how much you like the terminal,
but it's quite nifty not having to pull up a whole new UI to perform your
testing.

## Let's Talk GUI Apps

What's the obvious answer? Postman. if you've done API testing of any sort,
then you know this name. It's the industry standard. Born almost thirteen years
ago from this date and created by Abhinav Asthana in a time of apparent need,
Postman is potentially the most popular API (testing) platform to this date. If
you're interested in how it all started, check out [this Stack Overflow
thread](https://stackoverflow.com/questions/4797534/how-to-manually-send-http-post-requests-from-firefox-or-chrome-browser).

But maybe not so surprisingly, Postman has turned quite a number of people off
it in the past years. Their forced cloud sync and (almost) account requirement
didn't sit well with some people. I find it a little funny because a lot of the
time, you usually *want* to create an account to take advantage of cloud save
features, such as with VSCode or Jetbrains to sync IDE settings. However, this
isn't quite the case with API requests because there may or may not be
important information in them, such as an API key or something of the sort, and
who knows if that will keep you up at night or not. There are stories about
people having to switch off Postman because it no longer complied with their
company security practices too. Perhaps enough customers complained because to
their credit, they implemented the "Postman Vault" feature this year, allowing
users to store sensitive data locally for use in requests.

|![UI]({{ "/assets/img/2024_11_15_post/postman.png" | relative_url }})|
|:--:|
| *Not exactly an inviting first experience, is it?* |

This isn't a Postman hate post though. Despite what I am saying about it now,
Postman was a valuable testing tool that I have used quite a bit in the past.
They have a cross-platform desktop app and a web app as well, so it's quite a
versatile piece of software. If it's good enough for the industry, it's
probably good enough for you. You could end up loving it.

Now, if I propose Postman to you, then it's probably only fair that I also
mention Insomnia as well. It was basically the open source Postman alternative
for a while when Postman went the cloud route, offering many of the same useful
    features and an intuitive GUI to boot. Only, they also went the cloud route
    and force you to create an account with them to access core features of
    their client. Again, this shouldn't be a dealbreaker for most people, but
    perhaps there is something psychological about downloading software and
    then having to jump through extra hoops to use it properly. Who knows?

|![Insomnia]({{ "/assets/img/2024_11_15_post/insomnia.png" | relative_url }})|
|:--:|
| I'm tired, boss |

Now I could tell you about Hoppscotch too, which has gained a massive following
on Github. How about Yaak, from the same creator of Insonmia? But we could go
on for a long time about the many tools to test APIs.

Honestly though, I wasn't here to tell you about the big players. Now that we
have them out of the way, I can finally talk to you about my personal
favourites. For me, I am a fan of Bruno. Not just because they have a golden
retriever as their logo, but that's part of it... The key points that stand out
to me about Bruno are the following:

**Full client functionality enabled without account requirement**

You can download and use Bruno's full functionality out of the box - no
fiddling around with account creation first. The less hoops I need to jump
through before I can start using the software for its intended purpose, the
better.

**No forced cloud sync**

Plain text request collections offer great portability as an alternative.

You might be wondering whether this is even a good thing. Don't some people
want their collections synced and usable across machines? The good news is that
you can still do that via version control software thanks to Bruno's ability to
store collections in plain text files. That means you can manage and share your
collections with any version control system instead of someone else's cloud.
That being said, it does require all users to know how to use that version
control system, which seems likely but isn't a guarantee within teams. Bruno
actually has a Git UI for that situation, but it's not available in the free
version, which leads into my next point...

- ~~It's FOSS~~

Well, that's awkward. As I was writing this post, Bruno got rid of their
one-time purchase for the Golden edition and moved to a subscription model as
well!

|![Bruno's Github]({{ "/assets/img/2024_11_15_post/bruno_model.png" | relative_url }})|
|:--:|
| This is Bruno's Github page as of November 24 |

|![Bruno's Model]({{ "/assets/img/2024_11_15_post/bruno_new_model.png" |
relative_url }})|
|:--:|
| And this is what the link takes you to! |

But I'm not here to take a dig at Bruno. Dev time isn't free, after all. I just
found it funny that this was implemented while I was writing my post here.

All jokes aside, the free/open source version of Bruno is very capable, and it
avoids the dreaded cloud sync that has turned many people away from previous
tools. If you end up liking your experience and happen to also want access to
extra paid features like parameterized testing, a Git UI, and more, then you
can consider checking out their [paid
subscription](https://www.usebruno.com/pricing). For me, I am very happy with
the free version.

## A Last Word About API Testing In The Terminal

A while ago, I found myself going through some decision paralysis regarding GUI
versus command line tools. It seems a silly thing to get hung up on, but
sometimes the brain comes up with questions that even surprise yourself. I
thought, "Will I ever end up in a situation where I am stuck in a terminal and
therefore don't have access to my desktop app?"

In my experience, the answer was yes, but in those cases, I didn't have access
to my fancy command line tools either, so it didn't matter. So now that I have
that unrelated story out of the way, let me introduce you to httpie. As I
stated earlier, it is essentially a cURL alternative implemented in Python. You
can make requests with custom data and headers as you would with your desktop
HTTP clients, download files with it as you would with cURL, save responses by
piping them to files, and more.

So what are some useful features of httpie? For me, I like the following:

- Formatted + Colourized responses

httpie pretty prints JSON responses by default. This is the equivalent of
piping your cURL output into jq or the like.

- Interaction With Shell Scripting

I'll be honest, this isn't something that I've actually used httpie for, but
it's not so far-fetched to think that you could put a bunch of calls in a shell
script and run it like a collection. This is mainly accomplished by the
--check-status flag, which tells httpie to exit with an error code depending on
the response. Personally, I'm not enamoured with the idea since it's pretty
close to approaching automated tests, but perhaps it's okay for those quick and
dirty testing scenarios.

- Easy JSON Body Data Construction

httpie provides a simple syntax that lets you easily specify your key-value
pairs, also supporting your raw JSON needs. However, what I consider likely the
most convenient feature of httpie is the support for **nested JSON data**.
Writing out the raw JSON for a JSON array or object isn't so bad when it's for
a single value, but what about when that array or object is a value of another
JSON object? Then things start getting complicated. That being said, I am too
lazy to give you a custom example, so let me provide you with the one from the
docs instead:

![Nested JSON]({{ "/assets/img/2024_11_15_post/nested_json.png" | relative_url
}})

And there you go. The simplified syntax lets you easily construct JSON data
without worrying about whether you closed all your curly brackets...

**In Conclusion**

There is a lot more that I wish I could say, but this post is getting far too
long even for me. If you forgot the main point of this post, let me point you
in [the right direction](#read-this-if-you-dont-plan-to-read-the-post). For me,
it's Bruno and httpie. For you, it could be any of what we talked about above.
Don't overcommit to one option before seeing what the others have to offer!

Thank you for coming to my TED Talk, and I hope to see you again.

Until next time, peace 🦢
