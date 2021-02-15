Shell Wrapper And Runtime Modifier Manual
=========================================

This document will cover all variables and functions available by using SWARM. It might document functions or variables that are not yet available.

But if you find that something is missing, please contact me!

However, this is only for an overview, for full details on the functions some variables refer to, please see their according manpage.

But before we go into the use of SWARM in your own scripts, lets cover what arguments SWARM has:

Arguments
---------

* config		; This will start **cfg.edit** and provide a comfortable config editor for the cli
* demo			; This will show a demonstration script and show its code at the end.
* help			; You can pass a functionname to directly open the according manpage, or browse through the menu and read each manpage individualy
* log			; Shows the logfile
* new			; Pass: _script_, _function_ or _swarm_ to get some code/script
* words | phrases	; Prints a list of translateable strings (So if SWARM gets translated, those strings will be too)


Internal Arguments:
-------------------
* stats			; Just some stats of the project
* tar			; Creates ~/swarm-<build>.tar.gz, excl git repository / hidden files
* tarball		; Creates ~/swarm-full-<build>.tar.gz, incl git repository



Booleans
--------

___$isRO___

If **true** you cannot write on the machines filesystem. Either becuase it is Read-Only (RC) or due to the lack of permissions.


___$isDir___ <DIR>

This variable refers to _swarm.util.isdir_ which will return 0 if passed dir is found.


___$isROOT___

Returns **true** if _UID_ or _EUID_ is 0.


___$isGUI___

Returns **true** if $XDG_SESSION_DESKTOP is not empty (How to handle Wayland / Sway?)



Variables - Core Utils
----------------------

All these variables can be set before starting a script that uses SWARM to overwrite/bugfix possible errors due to commands that cant be found.

It is **MANDATORY** that you use these variables in scripts instead of the commands for cross-platform compatibility!


This could be done like:

    AWK=/usr/xpg4/bin/awk PRINTF=/usr/local/bin/printf  ./myscript


However, if you need to provide multiple 'fixes' - specialy if they seem to be permament,
it is recomend to refer to your SWARMRC directly.

    SWARMRC=$HOME/.swarmrc ./myscript


Obviously, this can only be done if you have write access to the system. If you havent,
you must provide an exising and prepared SWARMRC from somewhere else.

If this ever should be the case, PLEASE, send me a bug report or raise an issue on github
and provide the required information of the system and it's paths!


___$ECHO___

Uses either the builtin command or the physical file, prefers builtin.


___$PRINTF___

Uses either the builtin command or the physical file, prefers builtin.


___$AWK___

Refers to awk


___$GREP___

Refers to grep


___$SED___

Refers to sed


___$SU___

Refers to su, must be empty if not installed!


___$SUDO___

Refers to sudo, must be empty if not installed!


___$LS___

Refers to ls


___$MKDIR\_EXEC___

Refers to mkdir


___$MKDIR___

Refers to swarm.util.mkdir which uses __$MKDIR\_EXEC__


___$RMDIR___

Refers to rmdir


___$RM___

Refers to RM


___$TPUT___

Refers to tput


___$WHICH___

Refers to which


___$WHOAMI___

Refers to whoami


___$PWD\_EXEC___

Refers to pwd


___$HOSTNAME\_EXEC___

Refers to hostname


___$DATE___

Refers to DATE


___$DATE\_CUR___

This will print the current date in format: yyyy.mm.dd


___$DATE\_TIME___

Refers to the current time HH:MM:SS


___$DATE\_TIME\_LOG___

Refers to current time  HH:MM:SS.unixtime



Variables - Utils
-----------------


___$CURL___

Refers to curl.
This variable is not supposed to be used, please use the **download** function instead.


___$WGET___

Refers to wget
This variable is not supposed to be used, please use the **download** function instead.


___$CURLWGET___

Refers to the first available installed command (default if both avilable: curl)
This variable is not supposed to be used, please use the **download** function instead.


___$DD\_EXEC___

Refers to dd


___$DD___

Refers to swarm.util.dd which uses __$DD\_EXEC__


___$FIND___

Refers to find


___$MORE___

Refers to more


___$LESS___

Refers to less


___$MORELESS___

Refers to more or less, user settings (default if both available it selects _more_ automaticly)


___$FIND___

Refers to find



Variables - Paths
-----------------

___$SWARM_DIR_ROOT___

Refers to the path where the runtime file of SWARM is located


___$SWARM_DIR_DOCS___

This is where all the documentation has its place


___$SWARM_DIR_LANG___

Here, different languages could be found


___$SWARM_DIR_DATA___

This is the directory that contains all the data


___$SWARM_DIR_CONF___

This contains all the configuration files that are not part of the core


___$SWARM_DIR_LIBS___

This contains all functions that are not part of the core


___$SWARM_DIR_TEMPLATES___

This path contains folders like themese or the user configuration files


___$TMP_DIR___

This is the base dir for all tempfiles


___$SWARM\_USER\_DIR\_CONF___

This contains all the configuration files that are not part of the core


___$SWARM\_USER\_DIR\_LIBS___

This contains all functions that are not part of the core



Variables - Files
-----------------

___$LOG___

Refers to the log file, to be used in your scripts


___$TMP___

Refers to the default tmp file, to be used in your scripts


___$SWARM\_LOG___

Refers to the log file, for internal use


___$SWARM\_TMP___

Refers to the default tmp file, for internal use


___$SWARMRC___

Refers to the RC conf file (default: $HOME/.swarmrc ; Fallback: ./.swarmrc)



Functions - INIT & later
-------------------------

Functions defined here are for internal use only, as they refer to the __$SWARM_LOG__


___init.msg()___

Prints a message to the user during SWARM-init


___log___

Prints passed string to the $LOG file


___log.msg___

Prints message to the user during init and saves log file


___log.check___

Checks if **$LOG** can be written. If so, write **$DATE_CUR** to **$LOG** and sets **$isRO=false**
If it can not write the logfile, it sets **$isRO=true**

_This is done during init, no need to call it again!_



Functions - CORE
-----------------

___$FIND___

Refers to find


___$FIND___

Refers to find


___$FIND___

Refers to find
