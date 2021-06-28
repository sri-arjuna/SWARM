Troubleshooting:
================


While SWARM aims to run across different OS and distros, it may happen that you find an exoctic one.

If you cannot find a solution here, please send me the initial error messages as screenshot & text - and possible solution if you already found it.



An application could not be found:
----------------------------------

SWARM depends only on GNU Coreutils and BASH so if you get such an error,
chances are high that you have enountered a custom installation - or a 'limited' shell.

Either way, you might pre-pass the according variable prior to the invocation of the script,
or adjust them within the RC file which by default is created in _$HOME/.swarmrc_.

Or by prepassing a variable, which could look like this:

    AWK=/usr/share/gawk-whatever/gawk ./runtime


Likewise, if SWARM should not be able to detect your home directory properly:

    HOME=/home/myname ./runtime


However, in that case I would like/have to ask you to send me the output of:

    uname -a
    ls /
    source ./runtime >/dev/null ; printf '* %s\n' "$DISTRO" "$BASED" ; swarm.cleanup



Running SWARM on a Read-Only-System:
------------------------------------

/*
    THIS IS UNTESTED AREA
	- just explaining how it is supposed to work
	- according how I imagine these things to work
	- PLEASE send all feedback on practical issues
*/

I tried to move as many things into memory as possible, however, in some cases this is not possible.
For these situations, I require SWARM to create a RAMDISK for which the user must be root.

* Preset SWARM_RAMDISK=true ; This will force SWARM to use a RAMDISK wether the system is RO or not
* Optionaly, you may pass SWARM_RAMDISK_DIR=/path/to/mountpoint ; this will not force a RAMDISK!

Using a RAMDISK, it is intended to loose ALL data SWARM had created, this includes the $SWARMRC that is used a that point,
unless you force the 'local' RC file to be used.

This gives us these 2 example uses:
* If you want to test SWARM without anything created on your local disk (default: ~/.swarmrc & ~/.config/swarm)
    SWARM_RAMDISK=true
    ./runtime
* If your system became read only and you want to use your existing swarmrc.
    SWARMRC="$HOME/.swarmrc"
    ./runtime

However, this is all just for debugging.

___The only reason the RAMDISK 'usage' is available,
is to ensure that temporary files, that are required to execute certain SWARM functions, can be created.___

I have still to adjust the usage for non-rescue-scripts usage while system is RO...
Question is... does it make sense to execute scripts that cant do nothing as normal user because the system is RO?
-- Or would I 'loose data' (wrong user) when executing script as root?
