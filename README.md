# bash-custom

Bash with (tentative) preexec hook support

## Abstract

PREEXEC_COMMAND will be executed just before executing any command
on an interactive shell.  Unlike the traditional DEBUG trap trick,
this command will be executed only once for an entire (compound)
command, including a subshell command.  PREEXEC_COMMAND has a similar
semantics to PROMPT_COMMAND; it'll be only executed for interactive
commands, for example.  Use the history command to access the current
command.
