# bash-custom

Bash with preexec hook support

## Abstract

PREEXEC_COMMAND will be executed just before executing any command
on an interactive shell.  Unlike the traditional DEBUG trap trick,
this command will be executed only once for an entire (compound)
command, including a subshell command.  PREEXEC_COMMAND has a similar
semantics to PROMPT_COMMAND; it'll be only executed for interactive
commands, for example.  Use the history command to access the current
command.

## Caveats

I still don't know almost everything of the bash codebase.  This patch
seems to be working, but I have no idea if there are other states than
'global_command' that I should restore.  I wouldn't be surprised if
it's subtly broken.  However, I just replaced my preexec hook that
was running as the DEBUG trap with this and it seems to be working
pretty fine so far.

Unlike the DEBUG trap, PREEXEC_COMMAND doesn't set $BASH_COMMAND.
