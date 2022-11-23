---
layout: post
title: Random Thoughts About Vim 
subtitle: Your Friendly Unbiased Neighbour's Point of View
cover-img: /assets/img/VimImages/vimhelpme.jpg
thumbnail-img: /assets/img/VimImages/sadcat.jpg
share-img: /assets/img/VimImages/sadcat.jpg
tags: [Vim, Stories]
---

Hello everyone, it has been quite a while. I will spare you the details, but
I have been busy with work recently. I'm still pretty new, so I need to put in
a bit more time to learn the framework and get used to the daily routine.
Luckily, my team is quite accommodating, and I really appreciate them being
patient with me. 

Anyway, that isn't really what I meant to talk about. Instead, today we are
going to talk about a very famous text editor. No, not Emacs, not Sublime Text,
not Notepad. Actually, it's kind of funny because I was a pure Windows user for
a very long time and still kind of am, and Vim sure as heck doesn't come
installed on these machines. I'll get into why I picked it up later, but let me
start you off with a story.

Like I said above, I've been a Windows user for a very long time. I started
programming in university, and we started off with Python basics. Naturally, we
started off with the magic Python IDE Pycharm. My favourite Python IDE to this
day. Actually, it made the new user experience so smooth that I didn't even know
how virtual environments were created manually because it handled all of that
for me... Sorry, got a little off track. I took a course called CS2211 in
university, and this was really my first exposure to Linux-like systems. Hey,
where's Eclipse? Notepad++? That's weird. Of course, the text editor of choice
was Vim. What? coding assignments to be completed in Vim? Yeah, that's right.
We're not talking about souped-up Vim with plugins and a vimrc file that you've
spent dozens of hours tweaking. This was vanilla Vim running on a very
barebones Linux environment. 

Well, you can probably imagine how that went for a Windows user using Vim for
the first time. First of all, where are the menu buttons on the top of the
screen? Not really sure how I'm supposed to save anything, but I guess that's
fine. So I try to type a few words... but nothing shows up on the screen?
I guess the program is a bit buggy. That's fine. I can probably just close it
and re-open it. Except... huh? It's running in the terminal, and there's no
close button in the top right corner? How is anyone supposed to use this thing?
But luckily, my good friend Google was there to help me out, and a quick search
showed me that :q would get me out of there. Great, I've probably spent half
the lab time struggling to open and close Vim. So I hit the key combination,
and I can't quit for some reason. Something about unsaved changes? Well,
I enter :q! this time, and thankfully I get back to the terminal. So I run Vim
again, and I still can't enter any text. Turns out you have to hit the "i" key
to enter insert mode to enter text. Who could possibly remember that?

Whatever. I hit the key and enter a couple of lines of code. So far so good.
I guess that wasn't so bad, even if the identation was horrible and I had to
use the arrow keys to go back and forth between words to edit some typos. Now
the only thing left was to save. Again, why is there no save button? Google
tells me to enter :quit, so I do that and hit enter, but the line just shows up
in the code that I am currently editing. I'm stuck in Vim again, but this time
I can't even type the quit command to exit. No wonder Linux users are so
skilled. They have remember a hundred different commands just to use their text
editor properly. Miraculously, I find out that there's a normal mode in Vim,
and you can exit insert mode to get to it by hitting escape. That's awesome. At
least I can finish my tutorial now. I walk out of there feeling a lot less
confident than I walked in. 

You might be wondering what the point of that story was. Well, it should be
pretty clear that I didn't like Vim. Why would I ever use a text editor from
the 1990s when I can freely use full-blown IDEs that act as text editors and
more? Speed is a good reason. There honestly isn't any reason to break out the
Eclipse (lol) or VSCode if all you need to do is edit an HTML or markdown file. You
can, and there's nothing wrong with that, but one of these days you might find
yourself not wanting to wait those few seconds for your favourite IDE to open
up when you could open any other text editor almost instantly, and even quicker
when you can open it from the terminal. 

|![VimSplits]({{ "/assets/img/VimImages/vimsplitscreen.jpg" | relative_url }})|
|:--:|
| *Come on, that's pretty nifty. Any modern text editor can do this too, but
who's really keeping track?* |

However, speed wasn't my reason for wanting to learn Vim. I was more intrigued
by the idea of having a text editor with a set of keybindings and settings that
I could learn once and then take with me on any machine. And you will need them
at some point, to be fair. What do you think people use to edit scripts in the
terminal? Even more than that though, I simply loved the idea of mouseless text
editing, and I still do. Reaching for the mouse isn't the end of the world, but
why do it if you don't have to? 

However, at its core, Vim is a text editor. Let's forget about the insane
things you can do with regular expressions because that's more the magic of
regexes than Vim itself, and let's not get into the world of plugins because
you can spend far too much time trying to figure out what exactly you want.
Look, you want to jump around the file and change characters and words with
just your keyboard? You can do that. Maybe you're writing some HTML and want to
change everything between two tags or brackets. It's just three keystrokes. No
need to drag the mouse and select everything inside. Heck, maybe you just want
to add some text to the beginning or end of a set of lines. Visual block mode
has you covered.

Now maybe this all sounds very basic. Vim gurus, I got nothing on you guys. But
these shortcuts make text editing so much easier when you use them everyday,
and did I mention that they are portable? Any modern IDE has a Vim emulator of
some sort, so you can get the power of your favourite IDE with the familiarity
of your Vim keybindings. Again, Vim purists would cringe if they saw me saying
this, but this *is* a personal blog after all. I think I'm allowed to hold some
unpopular opinions haha. You know, like the Vim vs Neovim debate... but let's not
go there today.

So what's the verdict? I like Vim, but it has a steep learning curve at the
beginning that definitely turned me off of it the first few tries. It's a very
powerful text editor that most people, including myself, will probably never
get close to using all its features. At the same time, Vim isn't an IDE. You
can use it as one, of course. There are plugins for it, code completion among
other things (great for stuff like bashing out a Leetcode solution), but IDEs
have come a long way. You won't catch me trying to write an entire project in
Vim when VSCode is right there and has a Vim emulator. But hey, Vim is popular
for a reason. Give it a shot and see what you think. After all, there's only
  one way to find out.
