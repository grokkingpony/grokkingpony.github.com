---
layout: article
title: "Getting Started: Installing Pony and Tools"
description: "."
tags: [pony, installation]
---
All good tutorials start with installation.  This one is no exception.  I'm leaning (copying) heavily here from the info on the pony site, so please head over there to get the full scoop.


## Installing CLI tools
The best way to go on MacOS is to bootstrap yourself with the command-line tool ```ponyup```.  (Watch out, its in beta!). The [readme](https://github.com/ponylang/ponyup) gives you all the info you need.  Check you have it installed properly and added to your path by running the command ```ponyup version``` which will respond with the version you're running.

Once you have ```ponyup``` working you can use it to install the pony compiler, ```ponyc``` and the package manager, ```corral```.

    ponyup update ponyc release
    ponyup update corral release
    
Again, ask them for their versions to check they installed correctly.

    ponyc -version
    corral version
    
Note, the hyphen in the ```ponyc``` command. It's not needed for ```ponyup``` or ```corral```.

## Updating CLI tools
Running the command ```ponyup show``` will list the installed CLI tools and their versions.  The asterisk indicates the ones which are currently selected.

To update ```ponyc``` and ```corral``` just run the same commands that you used to install them in the first place. (See above.)

## IDE
There is minimal IDE support available for various IDEs and text editors.  I'm using VSCode (mainly because it's fashioable at the moment.)
