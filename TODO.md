Statement
---------
Framework core functions were written from scratch, again,
wheres most functions have been migrated from its initial form TUI.

Due to this, some issues are to be expected in the early public phases


Checklist upon adding new functions:
------------------------------------
1. Add english usage string in ./data/lang/en_GB/usage.conf
2. Verify 'function - usage' uses string from file ()
3. Put english manpage in ./docs/en_GB


Todo - PRE-release
------------------
* Fix status -C for swarm.util.rm
* Maintain /docs/contribute/manual.md for contributors and scrip-writers (maybe move to just ./docs ?)
* Verify ./runtime config provides all _menu_


1.0 Blockers
----------------------
* swarm - todo


TODO - POST-release
-------------------
* fix header (title?) theme issue (lines/tron)
* cfg.edit improvements
* swarm.util.dd ??
* swarm / project browser (give people time to get used to SWARM on a per-script level)
* cfg.set -a(ppend)?
* swarm.str.usb -> BSD ???
* download : certificates ??
* add roman2num :: https://www.unix.com/302928187-post7.html
* cp/mv: add bar dir/item [x/Y] if entry is a dir


Missing: Small Functions
----------------------
* the list move
* swarm.str.dirlist *dirtree


KNOWN ISSUES
------------
* swarm.str.usb			linux works, BSD/arm not so sure
* yesno ??			fix empty line in ssh session?
* ./runtime log			fix with dynamic FD's


Shellcheck recheck:
-------------------
* SC2162: read -r // gibt support für \.. will ich das?
* undo unset quoting // # shellcheck disable=SC2184
