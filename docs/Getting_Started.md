Getting started with SWARM
==========================

First things first, you can access all manpages either by browsing through the menu: **./runtime help**, or by directly accessing it by **./runtime help FUNCTIONNAME**.

I tried to be as meaningful aka self-explaining and short for all functions.
On some occasions it was not possible for compatibility reasons.

Here is a short overview of the most important functions:


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

* ask "question?" 	; catches any full text user input
* yesno "question?" 	; the 'yn' is provided by language file and is supported in code
* pick _[-a -m]_ $LIST 	; the 'select' wrapper, ; 0 (zero) will always be 'Back' and return 1 (back)



Application Handlers:
---------------------

* edit "file" 		; opens CLI or GUI appliaction
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



Writing a Basic Script:
-----------------------

First we have to understand that in order to provide these functions, we have to source the runtime.
For the best convenience, I do recomend to add _~/bin_ (or whateverplace you have your scripts stored) to your **PATH** variable via the _~/.bashrc_, this would be as simple as:

    PATH+="$HOME/bin"

If you now extract the SWARM tarball within _~/bin_ and if everything works well, you will have this path structure _~/bin/SWARM_.

Beeing in _~/bin_ enter the following in a console:

    SWARM/runtime new script full mytest.sh
    
   


