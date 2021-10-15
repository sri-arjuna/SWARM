This file is part of SWARM (Shell Wrapper And Runtime Modifier)
And shall guide you how to write functions for SWARM itself.

if you just want to use SWARM for your own scripts, you can skip this document!

Last Changed: 2021.10.06


Designated Audience
-------------------

	Code contributors, -patchers and everyone who wants to use the full benefit of SWARM


What this file does and what not
--------------------------------

* It is all about the syntax required to work best cross-plattform
* It is not about the commands provided with SWARM, but please see
  the [Manual](./MANUAL.md) for that too.


BASIC SYNTAX
============

This is a BASH framework, so in case of doubt, use BASH'ism.
* Use [[ condition ]]
* Use $(( 4 / 3 ))
* Use $( command ) 		; instead of ``
* Use ((C++)) / ((C+=5)) 	; where possible
* All functions returing a string to work with, must start with _swarm.str._
* All functions that aim to replace a coreutil, must start with _swarm.util._
* All functions that return a list, must start with _swarm.list._
* Functions that start with _swarm.print._ are supposed to be used by contributors, not script-authors. These are NOT shown in the help menu (./runtime help) (manpage is to be shown however)


BOOLEANS
========

All variables or function (sub-names) should start with either ___isYYY___ or ___beYYY___.

Examples are:

* $isRoot = swarm.util.isRoot
* $beVerbose in functions


LISTS
=====

Functions that return a list, must obey these points:
* Lists must be on multiple lines, as in: each item on its own line
* Lists must NOT be a single line ; exception are SWARM internal lists where it is verified that items do not contain spaces


FUNCTIONS
=========

Functions definitions shall take 3 lines,
with the first one providing the function name and its ARGS.
The next two (commented) lines shall be a descriptive text of the function.

	functionname() { # [options] ARG1 ARG2 ...
	# What it does
	# What it returns, unless covered by "What it does"
		echo code
	# Comment on next code block
		echo more code
	}

Sub-functions must have leading underscore to avoid beeing listed in the helpmenu.

	_functionname() { # string stuff

Furthermore, if a function returns an exit code - or using any other variable name that ___MIGHT___ be used in another function as well, it should __always__ be defined as local at the top of the function, and be assigned a default value.

	functionname() { # [options] ARG1 ARG2 ...
	# What it does
	# What it returns, unless covered by "What it does"
		local RET=1
		...


Statements: If...
================

___If then elif fi___ blocks should look like the following to provide enough (minimal) comments on what is done.

	if [[ condition ]]
	then	# Explanation
		...code...
	elif [[ condition ]]
	then	# Explanation
		...code...
	else	# Explanation
		...code...
	fi


Statements: case
================

There are 2 different 'defaults' to be applied, depending on what is done in each given case-statement.

If it is a short statement-block, each case can be a one-liner:

	case "$1" in
	1)	varX=X	;;
	2)	varY=y	;;
	esac

However, if there is more to be done, each statement must start with a comment explaining the following code:

	case "$1" in
	1)	# Doing this
		echo code
		echo more code
		;;
	2)	# Doing that
		echo code
		echo more code
		;;
	esac

Furthermore, if you do an 'option-check', please use the according template at SWARM/data/templates/function/while.

You can also access it directly by using:

	./runtime new function while


Other requirements:
------------------
* Always parse options first (and remove them with _shift_)
* Functions that require an argument, must fail with: swarm.help.usage "${FUNCNAME[@]}"
