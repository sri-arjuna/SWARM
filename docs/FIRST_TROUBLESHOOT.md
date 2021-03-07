Troubleshooting:
================


While SWARM aims to run across different OS and distros, it may happen that you find an exoctic one.

If you cannot find a solution here, please send me the initial error messages as screenshot & text.



An application could not be found:
----------------------------------

SWARM depends only on GNU Coreutils and BASH so if you get such an error, 
changes are high that you have enountered a custom installation - or a 'limited' shell.

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
