This file is part of SWARM (Shell Wrapper And Runtime Modifier)
And shall guide you how to write functions for SWARM itself.

if you just want to use SWARM for your own scripts, you can skip this document!

Last Changed: 2021.02.25



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
* Use $(( math / stuff ))
* Use $( command ) 		; instead of ``
* Use ((C++)) / ((C+=5)) 	; where possible
* All functions returing a string to work with, must start with _swarm.str._
* All functions that aim to replace a coreutil, must start with _swarm.util._
* All functions that return a list, must start with _swarm.list._
* Functions that start with _swarm.print._ are NOT shown to endusers (./runtime help) (manpage is to be shown however)

Lists
=====

Functions that return a list, must obey these points:
* Lists must be on multiple lines, as in: each item on its own line
* Lists must NOT be a single line ; exception are SWARM internal lists where it is verified that items do not contain spaces


Functions
=========

Functions definitions shall take 3 lines,
with the first one providing the ARGS.
The last two lines shall be a descriptive text of the function.

	functionname() { # [options] ARG1 ARG2 ...
	# What it does
	# What it returns, unless covered by "What it does"
		echo code
	}

Sub-functions must have leading underscore to avoid beeing listed in the helpmenu.

	\_functionname() { # string stuff

Other requirements:
------------------
* Always parse options first (and remove them with _shift_)
* Functions that require an argument, must fail with: swarm.help.usage "${FUNCNAME[@]}"
