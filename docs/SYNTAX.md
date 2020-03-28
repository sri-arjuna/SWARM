This file is part of SWARM (Shell Wrapper And Runtime Modifier)
and describes the best way to write the most cross-plattform
compatible scripts using SWARM.

Last Changed: 2020.03.13



Designated Audience
-------------------

	Code contributors, -patchers and everyone who wants to use the full benefit of SWARM



What this file does and what not
--------------------------------

	* It is all about the syntax required to work best cross-plattform
	* It is not about the commands provided with SWARM, but please see
	  the [./MANUAL.md]Manual for that too.




BASIC SYNTAX
============

As for all shells, there is always the question wether to use single or double brackets ([ , [[).

In case of doubt, always go with the double brackets!



Functions
---------

Functions definitions shall take 3 lines,
with the first one providing the ARGS.
The last two lines shall be a descriptive text of the function.

	functionname() { # [optionals] ARG1 ARG2
	# What it does
	# What it returns, unless covered by "What it does"
		echo code
	}
