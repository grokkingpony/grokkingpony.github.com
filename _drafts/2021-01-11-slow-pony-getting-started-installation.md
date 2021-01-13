---
layout: article
title: "Getting Started: Installing Pony and Tools"
description: "."
tags: [pony, ponyc, ponyup, installation, vscode, ide]
---
All good language introductions start with installation.  This one is no exception.  I'm leaning (copying) heavily here from the info on the [```ponyc``` git repo](https://github.com/ponylang/ponyc/blob/master/INSTALL.md), so please head over there to get the full scoop more directly.

## Installing CLI tools
The best way to go on MacOS is to bootstrap yourself with the command-line tool ```ponyup```.  (Watch out, it's in beta!). The [readme](https://github.com/ponylang/ponyup) gives you all the info you need.  Check you have it installed properly and added to your path by running the command ```ponyup version``` which will respond with the version you're running.

Once you have ```ponyup``` working you can use it to install the pony compiler, ```ponyc```.

    ponyup update ponyc release
    
Again, ask them for their versions to check they installed correctly.

    ponyc -version
    
Note, the hyphen in the ```ponyc``` command. It's not needed for ```ponyup```.

## Updating CLI tools
Running the command ```ponyup show``` will list the installed CLI tools and their versions.  The asterisk indicates the ones which are currently selected.

To update ```ponyc``` just run the same commands that you used to install them in the first place. (See above.)

## IDE
As Pony is so young (in language terms) there is probably less IDE support available than you'll be used to. That's one reason I'm doing this to be honest. Learning a language with less of a paved road in front of me feels exciting.  Plus, the [Pony community](https://www.ponylang.io/learn/#getting-help) is _great_.

Despite this, I'm not about to go back to the dark ages - and for me, that means I need some code-colouring.  For this there are a bunch of options. I've chosen to use [VSCode](https://code.visualstudio.com/) (mainly because it's fashioable at the moment).  To add Pony support to it, just install the [Ponylang extension](https://marketplace.visualstudio.com/items?itemName=gbtb.ponylang) from [gdtb](https://github.com/gbtb).

To get the full goodness of VSCode Problem Matcher (compile, full-syntax-checking, etc.) you need to add a new [VSCode Task](https://code.visualstudio.com/Docs/editor/tasks) as shown in [the Ponylang VSCode Plugin page](https://marketplace.visualstudio.com/items?itemName=gbtb.ponylang).

With this in place, you can start writing and compiling your Pony code with ease.
