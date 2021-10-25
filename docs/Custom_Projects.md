Create custom projects using SWARM
==================================

As SWARM is highly automated, you'll have to follow some few standarts and recomendations to get the most ouf it.

But lets get something straight here, this file does NOT describe how to write a single script, but a PROJECT that contains multiple folders and scripts! With custom configuration files and script-libraries that can be reused within your script-prroject!


Guide / Wizard:
---------------

So let us create that new project of yours:

    ./runtime new prj "My full project title"

This will start  guide / wizzards that will ask you some questions about your project.

Like, the 'main' filename, that will be executed from the commandline, this should be something short and without spaces.

There wille be serveral other questions, like wether or not you will want:
* a manpage
* a config file
* need/want  additional/custom 'source' files
* the directory name your project will be saved/created in
* and maybe more

Among these things, you'll be asked to provide:
* A script name ; this can be with or witout spaces, but does NOT reflect the script-filename
* The version of your script (if empty, it will defaul to 0.1)
* Your (the project-author) Name.

This information will be used to set these variables:
* $script_name
* $script_version
* $script_author

Which will be used to create hardcoded and 'linked' (by using the variable name) code for your project, like the manpage (hardcoded) or the --help screen ('linked').


LOGS:
-----

__IMPORTANT:__ $script_name will also be (re-)used if you want to use:

    swarm.log "Log entry"

As this will take care of several aspects by creating:

    $HOME/.config/swarm/logs/${script_name}.log

This will seperate days by adding the 'current' date as a 'title', and prepend every entry with the 'current' time and nanoseconds.

Of course this is absolutly optional. But highly recomended to use, if you want to support/have logfiles.


Terming of this Manual:
-----------------------

In the following I'll use certain terms to simplify explanations:

* execfile = The script filename that will be available within $PATH
* $CONF = Either a single file or multiple files referd to the directory only
* $BASE_DIR = The base directory where your dir-based menu will root at.
* <PRJ_DIR> = Something along: $HOME/prj/<PROJECT NAME>


Get started:
------------

After the project is created, usualy at __$HOME/prjs/<FOLDERNAME>__, but depending on your SWARM settings this might be somewhere different, you can start tweaking the files SWARM has created and adjust them to your needs.

Saying, for example, if you wanted a configfile, it will have created a template - but you will still need to write all the values there.

See: ___./runtime help cfg.edit___  to get the most out of SWARM, and to make it a lot more easy for your users to adjust their preferences with your project.

__NOTE:__ If you use the following within your execfile:

    swarm_tui -c <PATH_TO_CONFIG> $BASE_DIR

This will allow users to call:

    exefile conf[ig]

And select among multiple config files, where/if available.
This will work in the very same way as __SWARM/runtime conf[ig]__


More Variables:
---------------

By default, your execfile will create variables that are easy to reuse:

* $ME = execfile
* $ME_DIR = the absolute location of $ME/execfile
* $ME_CONF = Absolute path the config files or just the config dir if multiple files
* $ME_DIR_TMP = Absolute path to your custom temp dir: $HOME/.config/swarm/tmp/$script_name
* $ME_TMP = A dynamic named tempfile: $ME_TMP_DIR/$(swarm.str.genfilename ${SWARM_CODE}.tmp~)
