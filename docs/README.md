Shell Wrapper And Runtime Modifier - SWARM
==========================================
![GitHub release (latest by date including pre-releases)](https://img.shields.io/github/v/release/sri-arjuna/SWARM?include_prereleases) ![GitHub last commit](https://img.shields.io/github/last-commit/sri-arjuna/SWARM) ![Lines of code](https://img.shields.io/tokei/lines/github/sri-arjuna/SWARM) ![GitHub file size in bytes](https://img.shields.io/github/size/sri-arjuna/SWARM/tree/main/)

_SWARM is a framework to easily write application-like BASH scripts._

As SWARM does not need to be installed - hence **Runtime Modifier** -
it is great for scripts you carry on your usb-thumbdrive, like rescue scripts.

But the biggest bonus for portable scripts is the **Shell Wrapper** part.
Because we all know that not all distros install the same applications.

All this wile providing / showing a comfortable Text User Interface to the end-user!

It is a very new approach - yet overdue change - to scripting.
Yet, still works the very same way as you are used to from scripts.


3 Layers
--------

* The internal layer covers the handling between GUI/console (in case of calling external programs (like OS/system depending), or display status, etc - the 'internal code'), which makes the following API cross-plattform-compatible (me / contributors)
* The layer for script authors (you), the actual API / functions that SWARM provides
* And finaly the end-user layer (the wrapper visual outputs, incl settings on themes and language)

___As an example:___
SWARM provides functions to automaticly open available applications to _edit_, browse the _web_, use a _filemgr_ or open other _terminals_, depending wether the user runs the script in X/Wayland or TTY.
And that is on systems it was never run before, once configured (automaticly, first usage), it will open your favorite applications for each given task.
On top of that, some systems have sudo, others have just su available, execute commands that requires root access with _asRoot_.

So you as a script-writer, no longer have to worry which __editor__ is installed when a user is in a GUI session.
Because we all know how.. dissapointing... it can be to have to edit a file in vi or nano, while your atom or sublime is open on another screen.

On top of that, using SWARM will generate its output according to a configured _theme_,
so all output the user will see is consistant to her or his preferences.

Saying, interested users can switch to (or create/change a) __theme__ that matches their console/terminal settings / style.


Features:
---------

* Output can be aligned to: _left_, _center_ and _right_
  Using easy to remember commans like: *header*, *title* and *printe* (as echo/printf)
* INIT style status messages
  Using: *bar* and *status*
* Consistend wrapper (visual & code) output for _select_ and other _read_ tasks
  Using: *pick*, *ask* and *yesno*
* Many more (135+) 'smaller' (and bigger) functions that can be very helpfull for your project/s.


Target Audience:
----------------

* Commandline enthusiasts
* System Administrators
* Anyone interested in scripting

Basicly everyone one who wants or has to write comfortable scripts for themself, the community and/or for (their) end users.


Whats the purpose?
------------------

The main goal was **swarm**, the function named like the project,
which is they key function to the initial project of mine named: **Script-Tools**

This functions main purpose is to browse directories, list and execute scripts
from with the 'browser' but also beeing able to pass directores, scripts and their options
and values directly to the script which passes the arguments down the specified script.

All this while beeing highly customizeable, like showing the content of a defined textfile as
a general info while browsing, or showing a specific 'help' (if passed) for folders
when called from the command line.

The idea for something like this was born back in 1995, but it was not until 2011,
when I decided to 'go all GNU+Linux' that I had an actual idea how to realize it.

Long story short, I would like to ask everyone who is writing scripts with SWARM,
to particpiate in the project: _"Script-Tools"_ of mine, which aims to be a tool for cross-platform -
as in across all kind of distros a configuration, tweak, rescue and fun tool.

As in, but not limited to:
* Select & apply GRUB(2) themes
* Change keyboard layout
* Tweak login managers
* Manage & Connect: Wireless Networks & NAS/SAN
* EFI handler

So if you are either interested in this tool as such, or hopefully even in participating,
please have a look here:
* [Script-Tools](https://github.com/sri-arjuna/script-tools)

Otherwise, I hope you enjoy writing scripts with SWARM as much as I do.


Pseudo installation
-------------------

While SWARM does not need to be installed, it is most comfortable to have its folder
in the path where you have all the scripts you execute from the terminal.

In most cases this probably is: $HOME/bin

But of course you can re-use whatever other path you might have in use.

If you have nothing like this just yet, lets make it:

    mkdir "$HOME/bin"
    echo 'PATH+=":$HOME/bin" >> "$HOME/.bashrc"
    cd "$HOME/bin"
    git clone "http://github.com/sri-arjuna/SWARM.git"

Read the [First Steps](./docs/First_Steps.md) from here on.


Reason why?
-----------

1. Why BASH?
Because BASH is pre-installed on most GNU+Linux and/or *BSD variants.
And where it is not, it is available in the Repo.

2. Why not something else?
I did consider C, but I did not want to compile. (see 3.)
Also Python was considered, but with neither the C- nor Python solution
"runtime" would have been an option - or would have lost alot of its scripting-comfort.
Not much else available on minimal installations.

3. Why did you not want to compile?
Just in case we get Fallout 5 in RealLife (Corona, etc) and everything falls apart,
I wanted anyone who finds it on such a lost Vault-Tec terminal to be able to direclty
make the changes they need. Thus, SWARM beeing itself all in plain-text is essential to me.


LINKS:
------

* [GitHub](http://www.github.com/sri-arjuna/SWARM)
* [Patreon](https://www.patreon.com/script_tools?fan_landing=true)
* [Reddit](http://www.reddit.com/r/SWARM_BASH)


CREDITS:
--------

* FedoraForum.org ; Staff & Members
* UNIX.com ; Staff & Members
* All my discord friends who had to endure my brabeling about SWARM while they dont use *nix based systems.


BETA TESTERS
-------------

* BMT (PONYMODZ @ github)


ALPHA TESTERS
-------------

* lsatenstein @ fedoraforum.org
* Chubler_XL @ unix.com


KNOWN ISSUES
------------

* iMac / Apple users must manualy update their BASH to 4.3 (or higher) using homebrew, see this [StackExchange Article](https://apple.stackexchange.com/questions/193411/update-bash-to-version-4-0-on-osx/197172#197172)
