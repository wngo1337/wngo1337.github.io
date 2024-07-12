---
layout: post
title: Using Meld On Mac - A Tale of Frustration
subtitle: How Far Would You Go For Your Merge Tool?
cover-img: /assets/img/2024_07_11_post/screaming_cat.jpg
thumbnail-img: /assets/img/2024_07_11_post/screaming_cat.jpg
share-img: /assets/img/2024_07_11_post/screaming_cat.jpg
tags: [Meld, Git, Stories]
---

Hey, it's William. Today we're going to talk about the shockingly bad
experience of getting Meld to work as your mergetool on a Mac!

Now, you might be wondering why anyone would be using Meld in 2024. After all,
it is admittedly over two decades old, not to mention how VSCode can even be
configured as a cross-platform mergetool these days in addition to its role as
a development environment. Actually, that was exactly what I was using before I
remembered Meld. The truth is that I just wanted to use a dedicated mergetool
and see if there was anything special about it. Well, that and I needed a
really simple GUI mergetool that I could pull up from WSL2. WSL is a
surprisingly capable programming solution when you can't quite make the switch
to Linux, but that's a story for another time.

|![VSCodeAsAMergetool]({{ "/assets/img/2024_07_11_post/vscode_mergetool.png" | relative_url }})|
|:--:|
|*VSCode's 3-way merge editor. No, this is not my image. I stole it from the VSCode website.*|

I figured that the installation process could hardly be more difficult than
downloading and running the installer, but imagine my surprise when I found out
that Meld isn't officially supported on macOS. Luckily, some good people
packaged up Meld for MacPorts, so I grabbed the port and just tried running it.
For reference, I'm running Sonoma 14.5. Of course, it failed to even start.
Unfortunately, I didn't save the error logs, but I'm pretty confident that it
was something along the lines of this:

```
% meld 2022-04-07 17:36:21,148 CRITICAL Gtk:
_gtk_style_provider_private_get_settings: assertion
'GTK_IS_STYLE_PROVIDER_PRIVATE (provider)' failed 2022-04-07 17:36:21,148
CRITICAL Gtk: _gtk_style_provider_private_get_settings: assertion
'GTK_IS_STYLE_PROVIDER_PRIVATE (provider)' failed 2022-04-07 17:36:21,148
CRITICAL Gtk: _gtk_style_provider_private_get_settings: assertion
'GTK_IS_STYLE_PROVIDER_PRIVATE (provider)' failed zsh: segmentation fault meld
```

So that was a pretty bad start. I did some searching, and I came across an
article stating that Meld has a dependency on XQuartz to properly run. Granted,
the article was probably about a decade old, but information is information.
Either way, I wasn't expecting that much, but the program's UI actually opened,
to my surprise. The colours were inverted and the text hardly legible, but it
seemed like I was making progress. I restarted the program thinking that it
could just be a buggy startup, but I didn't expect that the program would never
open again regardless of what I tried... It was a very disappointing result,
and I had no choice but to uninstall the port.

At this point, I decided to go in a different direction. I found
<https://yousseb.github.io/meld/> and it looked very promising. A fork for Meld
packaged specifically for Mac, and standalone installers as well. Now, I
probably should have checked when exactly the last update was or noticed that
the last release on the site was for Catalina, but I simply expected the latest
version to be just that. Nonetheless, the result seemed to be even better than
the last try. The UI opened, I had my 3-pane merge view opened, and I could
actually click the buttons on the side panes to merge in code blocks.
Everything was looking good until I tried to merge in code from both sources,
and the program crashed unexpectedly. I tried again, it crashed again. I
considered whether I could live with this issue and manually enter the changes
from the second source. I could not.

I uninstalled this version of Meld as well and checked out the Github repo at
<https://github.com/yousseb/meld>. Then I found
<https://github.com/yousseb/meld/issues/147> which was a 151 comment thread
entirely about Meld breaking on Sonoma! Surely there would be a working
solution in there, and there was. Turns out that the website in the above
paragraph was rather outdated, and the author had indeed repackaged it for
Sonoma. Not only that, but user syneart had written a hot-fix script to
automatically fix additional installation issues as well. You can find the post
here: <https://github.com/yousseb/meld/issues/147#issuecomment-1907274384>

After going through those steps, I could finally run Meld without issue, or so
it seemed. I made up a simple merge scenario and opened up the file in Meld...
only for Meld to show three blank panes, telling me in each one that it could
not locate the requested file. For reference, I added these lines (as specified
in the github.io link) to my .gitconfig to set Meld as my default mergetool:

```
[diff] tool = meld [difftool]
    prompt = false
[difftool "meld"]
    trustExitCode = true
    cmd = open -W -a Meld --args \"$LOCAL\" \"$REMOTE\"
[merge]
    tool = meld
[mergetool]
    prompt = false
[mergetool "meld"]
    trustExitCode = true
    cmd = open -W -a Meld --args --auto-merge \"$LOCAL\" \"$BASE\" \"$REMOTE\" --output=\"$MERGED\"
```

It seemed that Meld was somehow looking for this file in the root directory
rather than the current working directory, which was incredibly odd because
this was not an issue even in the earlier versions that I had used. Now, you
may choose your desired solution from
<https://github.com/yousseb/meld/issues/73>, but I went with the easiest one
that simply prepends the current working directory to the path of the file
being opened, and after many hours of wading through oudated versions, old
solutions, and Github issues, I was finally able to use Meld without issue.

|![MeldMergeTool]({{ "/assets/img/2024_07_11_post/meld_mergetool.gif" | relative_url }})|
|:--:|
| *Meld in all its simply glory.*|

Now after all this struggle, it's possible that you are wondering if I think
that was worth all the trouble, and my answer to that would be "probably". I
love discovering new (or not so new) software that is reliable and
**cross-platform**, I love being able to use the same interface across
different operating systems, and I like having dedicated tools for certain
tasks. The thing is that again, VSCode offers this functionality out of
the box. There are also other very capable mergetools like WinMerge, Sublime Merge, Beyond
Compare (not free), KDiff3, p4Merge, etc. At the end of the day, you just need
one working mergetool for your workflow, and I found mine. Fingers crossed that
it doesn't break the next time MacOS updates 🤣

Until next time, peace 🦢
