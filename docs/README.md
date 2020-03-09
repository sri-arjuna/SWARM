Shell Wrapper And Runtime Modifier - SWARM
==========================================

_SWARM is an user interface for bash scripts._



Overview
--------

You want scripts that work nice in GUI and console,
on different plattforms, therefor with different bash builddirs
and still work?

You want the end user to edit files,
but dont know what applications they might have installed?

Always thought that such a wide terminal window looks empty?
Did you ever thought it would be nice to have text left, right and even centered?

You want to structure your scripts in folders
and access scripts in there from the command line?

**SWARM covers all this and more!**

While it parses for default applications for tasks, in both CLI and GUI modes,
like text-editors, internet browsers, file managers or internet commands such as wget or curl,
it also lets the user configure their preferences to be used automaticly by other SWARM scripts as well.

It has handlers for yesno, select download, progressbar and lots more.
Also you do not have to worry about the different functionalities of readline, echo or print.
Since for those are 'wrappers' as well, to give you the benefit of text orientation.

And that still is not all!


Examples:
---------








Basic usage:
------------

Or - how to get all the stuff:

When actualy using in runtime, you would call it like:


    #!/usr/bin/env bash
    source ./SWARM/rc


And when calling an installed version of SWARM:


    #!/usr/bin/env bash
    #swarmrc-<buildnumber>
    source swarm-2234


This way multiple instances of SWARM can be installed in paralell.






CREDITS & Sources:
------------------
* FedoraForum.org ; Staff & Members
* UNIX.com ; Staff & Members, special thanks to mod: Peasant for the name suggestion!
