Shell Wrapper And Runtime Modifier - SWARM
==========================================

_SWARM is a user interface for bash scripts._


SWARM's objective is to provide scripts that work nicely in GUI, console and platform independent interfaces.
SWARM is a wrapper for different bash builds and bindirs.
With SWARM they will work everywhere as long there is a bash shell!

The first Text User Interface Framework that does not need to be installed.

SWARM tries to make coding easier for script-authors, usage more convenient for endusers and handle installed application for both of them.
So it provides a 3-way interface between script author, enduser and the computer.


Overview
--------

Always thought that such a wide terminal window looks empty?
Did you ever think it would be nice to have text to the left,
to the right, and even aligned to the center??

You want the end user to edit files, but dont know what applications,
like leafpad or gedit, they might have installed?

Ever wanted to have your scripted projects sorted in different directories
but still want them to share some of the same functions / variables?


**SWARM covers all this and more!**

While it parses for default applications like "text-editors, internet browsers, file managers
or internet commands such as wget or curl", it manages  both CLI and GUI modes.
SWARM also lets the user configure their desired preferences to be used automaticly
by other SWARM scripts as well.

It has handlers for "yesno", "select" "download" (curl/wget), "progressbar" and  more,
so they are fully integrated into the (custom?) theme you had set for SWARM.
You do not have to worry about the different functionalities of read and echo.
SWARM has 'wrappers' for these as well, with the aim to give you the benefit of text orientation.

And that still is not all!


Basic usage:
------------

Or - how to get all the stuff:

When actualy using in runtime, you would call it like:


    #!/usr/bin/env bash
    source ./SWARM/runtime


This loads several functions into memory that you can use now.
I tried to give them short and reasonable names.

All 'color' references are to the __default-blue__ theme!

* header "left" "center" "right" ; All blue background with white text
* title "my title" ; All white background with blue text, and blue borders
* printe "left" "center" "right" ; blue borders, next output is on a newline
* printl "left" "center" "right" ; blue borders, next output overwrites this
* yesno "question?" ; the 'yn' is provided by language file and is supported in code
* ask "question?" ; catches any full text user input
* pick _[-a -m]_ $LIST ; the 'select' wrapper, ; 0 (zero) will always be 'Back' and return 1 (back)
* status $? "Left" "Center"
* rnd _[max | min max ]_ ; prints a random number between 0-100; or 0-max.
* edit "file" ; opens CLI or GUI appliaction
* files "path" ; opens CLI or GUI file manager
* web "url" ; opens CLI or GUI web browser
* bar _[options]_ min max val ["text"]
* cfg.list "file" ; Lists all bash-based keys (variables) of the given file
* cfg.get "file" var
* cfg.set "file" var "val"
* download "url"
* swarm _[options]_ "path" ; THE purpose of doing all this, everything else is just a gimmick ;)

These are the core basics.
Everything else provided is just for additional convenience.

If strings should become too long to be displayed properly
within the consoles border, SWARM will break up the strings
and and try to keep the intended text alignments/orientations.

This ensures that the scripts keeps it's intended look and feel
even with different sized gui terminal windows.



CREDITS & Sources:
------------------
* FedoraForum.org ; Staff & Members
* UNIX.com ; Staff & Members, special thanks to mod: Peasant for the name suggestion!
