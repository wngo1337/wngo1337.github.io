---
layout: post
title: I Made a Virtual Soundboard Out of TV Show Lines
subtitle: JavaFX Program With GUI to Activate Audio Clips
cover-img: /assets/img/fillmore/vallejo.jpeg
thumbnail-img: /assets/img/fillmore/fillmoreskate.jpeg
share-img: /assets/img/fillmore/fillmoreskate.jpeg
tags: [Java, JavaFX]
---

Hey guys, it's me again. Today we're going to be taking a look at a little project using the [JavaFX library](https://openjfx.io/). It's generally used to create desktop applications and is more up-to-date than the long-lived Java Swing. It's also cross-platform so you could theoretically use it to build mobile applications too, but I'm not quite sold on that part haha. 

If you aren't familiar with Fillmore!, you can read more about it [here](https://en.wikipedia.org/wiki/Fillmore!). At its core, the show is a child-friendly parody of police dramas from back in the day. It centres on former delinquent Cornelius Fillmore and his partner, Ingrid Third as they solve school "crimes." I liked watching it back in grade school but only really developed an appreciation for it when I got older. I recommend that you give it a shot if you have time.  

So you might be thinking, "Why use JavaFX? No one builds desktop applications anymore." That's probably true, but at the same time it's great to have a GUI toolkit at your disposal for personal projects. Also, the practice with a tree structure in the form of JavaFX's scene graph isn't bad either.

Anyway, my intention was to use Gluon's nifty drag and drop Scene Builder to build my user interface. It automatically creates FXML files based on your scene, and those can be read by your application to change what it displays, essentially implementing a model-view-controller architecture. 

The only problem? I can't use Scene Builder here. Scene Builder is really great for complex, static layouts because it generates all the FXML for you, but it's less flexible because you have to manually specify what function each JavaFX node corresponds to. You can probably imagine how difficult it would be to create and manage functions for a large number of buttons. That means we have to do it the old-fashioned way and code our GUI in Java.

Luckily, our application is quite small and simple so that isn't too difficult. We just create the root node which is the main container of the window we want to display, and then we can populate it with text, images and more. The main workhorse of this application is this method that accesses the files of a directory, creates buttons from them, and then adds them to a container. 

(IMAGE HERE)

When we're done, the application looks like this.

Whenever a button is clicked, it plays the corresponding sound clip. That's the entire program! I wasn't kidding when I said it was simple. 