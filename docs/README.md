Shell Wrapper And Runtime Modifier - SWARM
==========================================

_SWARM is a framework to write application-like BASH scripts._


As SWARM does not need to be installed - hence **Runtime Modifier** -
it is great for scripts you carry on your usb-thumbdrive, like rescue scripts.

But the biggest bonus for portable scripts is the **Shell Wrapper** part.
Because we all know that not all distros install the same applications.
SWARM provides functions to automaticly open available applications to _edit_, browse the _web_, use a _filemgr_ or open a _terminal_, depending wether the user runs the script in X or TTY.
And that is on systems it was never run before, once configured, it will open your favorite applications for each given task.

On top of that, using SWARM will generate its output according to a configured _theme_,
so all output the user will see is consistant to her or his preferences.



Whats the puprose?
------------------

The main goal was **swarm**, the function named like the project.

This functions main purpose is to browse directories, list and execute scripts
from with the 'browser' but also beeing able to pass directores, scripts and their options and values directly to the script which passes the arguments down the specified script.

All this while beeing highly customizeable, like showing the content of a defined textfile as a general info while browsing, or showing a specific 'help' (if passed) for folders when called from the command line.

The idea for something like this was born back in 1995, but it was not until 2011,
when I decided to 'go all GNU+Linux' that I had an actual idea how to realize (and what to use for).


But the real goal the started all this was my "sea's scripted tools" project,
which aims to have scripts that serve as solutions that work on minimal
installations as well as rescue tool that is EASY to use - even in rescue mode.

You could do fun things like:
./sst boot grub2 theme solar
./sst connect wifi
./sst connect nas _\[LABEL\]_

From starting that single project until realizing that I had to extract all 'visuals' and other
'general functions' to TUI, was about a 5 year process, but required an installation.
Now, another 5 years later, it became SWARM.



Use cases:
----------

For 100% single task scripts, SWARM is best placed in something like $HOME/bin\[/SWARM\].
For projects that contain multiple scripts, I recomend to place SWARM inside the project directory.

Whatever you do, unless the script is invoked by **swarm**, the **SWARM** directory
must be in the same directory as the executed script.
Only this verifies proper handling.



Reason why?
-----------

1. Why BASH?
Because BASH is pre-installed on most GNU+Linux and/or *BSD variants.
And where it is not, it is available in the Repo.

2. Why not something else?
I did consider C, but I did not want to compile.
Also Python was considered, but with neither the C- nor Python solution
"runtime" would have been an option.
Not much else available on minimal installations.

3. Why did you not want to compile?
Just in case we get Fallout 5 in RealLife (Corona, etc) and everything falls apart,
I wanted anyone who finds it on such a lost Vault-Tec terminal to be able to direclty
make the changes they need.
Yeah baby, Steam-Punk! :D



What are scripts good for?
--------------------------

* Scripts are great to summarize commands that are either often repeated or hardly ever used.
* Scripts should simplify certain tasks with the most minimal tools available.
* Scripts should be informative and easy to use
* 1 script should only do 1 thing

But while scripts should not be applications, there is no other (faster) way to
give your scripts the same power for different projects, cross-distro-compatible,
without the need to install anything to have a decent interface to present to endusers.

We live in 2021, so the overhaul for bash scripts is long overdue! ;)



Basic usage:
------------

Or - how to get all the stuff:

When actualy using in a script, you would call it like:


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
* tui _[options]_ "path" ; THE purpose of doing all this, everything else is just to comfort this ;)

These are the core basics.
Everything else provided is just for additional convenience.

If strings should become too long to be displayed properly
within the consoles border, SWARM will break up the strings
and and try to keep the intended text alignments/orientations.

This ensures that the scripts keeps it's intended look and feel
even with different sized gui terminal windows.

LINKS:
------

* http://www.reddit.com/r/SWARM_BASH
* http://www.github.com/sri-arjuna/SWARM        TODO


CREDITS:
--------

* FedoraForum.org ; Staff & Members
* UNIX.com ; Staff & Members, special thanks to mod: Peasant for the name suggestion!
* https://community.unix.com/t/blog-thread-creating-a-shell-wrapper-and-runtime-modifier-swarm/377390/48


Alpha Testers
-------------

* lsatenstein @ fedoraforum
* Chubler_XL @ unix
