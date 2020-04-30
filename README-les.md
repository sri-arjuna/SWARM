Shell Wrapper And Runtime Modifier - SWARM
==========================================

_SWARM is a user interface for bash scripts._



Overview
--------

SWARM's objective is to provide scripts that work nicely in GUI, console and platform independent interfaces.
SWARM is a wrapper for different bash builds and bindirs. With SWARM they will work everywhre there is a bash shell?

You want the end user to edit files, but dont know what applications, like leafpad or gedit,
they might have installed?

Always thought that such a wide terminal window looks empty?
Did you ever think it would be nice to have text to the left,
to the right, and even aligned to the center??

SWARM encourages you to structure your scripts inside folders and provides access those scripts.

**SWARM covers all this and more!**

While it parses for default applications like "text-editors, internet browsers, file managers 
or internet commands such as wget or curl", it manages  both CLI and GUI modes.
it also lets the user configure their desired preferences to be used automaticly 
by other SWARM scripts as well.

It has handlers for "yesno", "select download", "progressbar" and  more.
You do not have to worry about the different functionalities of readline, echo or print.
SWARM has 'wrappers' for these as well, with the aim to give you the benefit of text orientation.

And that still is not all!


Examples:
---------








Basic usage:
------------

Or - how to get all the stuff:

When actualy using in runtime, you would call it like:


    #!/usr/bin/env bash
    source ./SWARM/runtime


And when calling an installed version of SWARM:


    #!/usr/bin/env bash
    SWARM_INSTALLED_DIR=/var/opt/swarm-2
    source $SWARM_INSTALLED_DIR/runtime


This way multiple instances of SWARM can be installed in paralell,
to ensure cross-version compatibility.
The '-2' refers to SWARM's build (Nr. of executed 'git push master').


This loads several functions into memory that you can use now.
I tried to give them short and reasonable names.

All 'color' references are to the __default-blue__ theme!

* header "left" "center" "right" ; All blue background with white text
* title "my title" ; All white background with blue text, and blue borders
* printe "left" "center" "right" ; blue borders, next output is on a newline
* printl "left" "center" "right" ; blue borders, next output overwrites this
* choose $list or "${ARRAY[@]}" ; 0 (zero) will always be 'Back' and return 1 (back)
* ask "question?" ; the 'yn' is provided by language file and is supported in code
* status $? "Left" "Center"
* rnd _[max | min max ]_ ; prints a random number between 0-100; or 0-max.
* edit "file" ; opens CLI or GUI appliaction
* files "path" ; opens CLI or GUI file manager
* web "url" ; opens CLI or GUI web browser


__2nd Iteration__
* bar _[options]_ min max val ["text"]
* cfg.list "file" ; Lists all bash-based keys (variables) of the given file
* cfg.get "file" var
* cfg.set "file" var "val"
* configure [path | file]; configures SWARM or the provide file or path


__3rd Iteration__
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
