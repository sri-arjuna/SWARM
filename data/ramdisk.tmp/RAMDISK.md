RAMDISK
=======

This directory is used for the loop of the ramdisk.

Please do not write anything into this directory.
It only exists as emergency backup to be able to start SWARM 
on a system it was never used before - even if it is Read-Only - 
but it does require root access to do so.

However, this means you still can refer to "$SWARM_TMP" and use it as your tempfile.
Note that this directory will become **$SWARM_USER_DIR_BASE**.

If you work on emergency scripts, you might want to use these bool-varibles to define which directory to work in:

    if $isRO && $isRoot && $SWARM_RAMDISK
    then	printe "This should refer to ramdisk.tmp:" "$SWARM_USER_DIR_BASE"
    		swarm.list.dirs "$SWARM_USER_DIR_BASE"
    fi

