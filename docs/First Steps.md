First Steps with SWARM
======================

First things first, you can access all manpages either by browsing through the menu: **./runtime help**, or by directly accessing it by **./runtime help FUNCTIONNAME**.

I tried to be as meaningful and self-explaining and short for all functions.
On some occasions it was not possible for compatibility reasons.

For 100% single task scripts, SWARM is best placed in something like _$HOME/bin\[/SWARM\]_.
For projects that contain multiple scripts, I recomend to place SWARM inside the project directory.

Whatever you do, unless the script is invoked by **swarm**, the **SWARM** directory
must be in the same directory as the executed script.
Only this verifies proper handling.


Basic usage:
------------

Or - how to get all the stuff:

When actualy using in a script, you would call it like:


    #!/usr/bin/env bash
    source ./SWARM/runtime



Get your first Script:
----------------------

First we have to understand that in order to provide these functions, we have to source the runtime.
For the best convenience, I do recomend to add _~/bin_ (or whateverplace you have your scripts stored) to your **PATH** variable via the _~/.bashrc_, this would be as simple as:

    PATH+="$HOME/bin"

If you now extract the SWARM tarball within _~/bin_ and if everything works well, you will have this path structure _~/bin/SWARM_.

Beeing in _~/bin_ you now create files with the following content:

    #!/usr/bin/env bash
    source ./SWARM/runtime

Or enter the following in a console, to get a slightly more advanced template to work with:

    SWARM/runtime new script full mytest.sh
    

Here is a short overview of the most important/casual functions that are now available:
(_Feel free to browse through_ **./runtime help** _to get to know all functions and directly read their according manpages._)



Basic Visuals
-------------

* header "left" "center" "right" 	; All blue background with white text
* title "my title" 			; All white background with blue text, and blue borders
* printe "left" "center" "right" 	; blue borders, next output is on a newline
* printl "left" "center" "right" 	; blue borders, next output overwrites this
* status $? "Left" "Center"		; Prints a colored 'exit-code-string' based on $?
* bar _[options]_ min max val ["text"]	; Prints different kind of progress / working


User Interactions:
------------------

* ask "Question?" 	; catches any full text user input
* yesno "Question?" 	; the 'yn' is provided by language file and is supported in code
* pick _[-a -m]_ $LIST 	; the 'select' wrapper, ; 0 (zero) will always be 'Back' and return 4 (back)
* press	["Text"]	; Simply ask the user to press enter to continue


These are the core basics.
Everything else provided is just for additional convenience.

If strings should become too long to be displayed properly
within the consoles border, SWARM will break up the strings
and and try to keep the intended text alignments/orientations.

This ensures that the scripts keeps it's intended look and feel
even with different sized gui terminal windows.


Application Handlers:
---------------------

* edit "file" 		; opens CLI or GUI application
* filemgr "path" 	; opens CLI or GUI file manager
* web "url" 		; opens CLI or GUI web browser
* download "url" 	; Downloads an URL


Handy Tools:
------------

* cfg.list "file" 		; Lists all bash-based keys (variables) of the given file
* cfg.get "file" var		; Retrieves the value of 'var' in 'file'.
* cfg.set "file" var "val"	; Sets the value of 'var' to 'val' in 'file'
* cfg.edit "file"		; Full fledged conf file editor, with customizable multiple-choice-options
* rnd _[max | min max ]_ 	; prints a random number between 0-100; or 0-max.



