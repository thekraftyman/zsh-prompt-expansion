# Prompt Expansion

## Expansion of Prompt Sequences

### Special Characters

| Import | Output |
|--------|--------|
| %%     | %      |
| %)     | )      |

### Login Information

| Import | Output |
|--------|--------|
| %l | The line (tty) the user is logged in on, without ‘ /dev/ ’ prefix. If the name starts with ‘ /dev/tty ’, that prefix is stripped.                                                                   |
| %M | The full machine hostname.                                                                                                                                                                          |
| %m | The hostname up to the first ‘.’. An integer may follow the ‘%’ to specify how many components of the hostname are desired. With a negative integer, trailing components of the hostname are shown. |
| %n | $USERNAME.                                                                                                                                                                                          |
| %y | The line (tty) the user is logged in on, without ‘/dev/’ prefix. This does not treat ‘/dev/tty’ names specially.                                                                                    |

### Shell State

| Import | Output |
| %# | A ‘#’ if the shell is running with privileges, a ‘%’ if not. Equivalent to ‘%(!.#.%%)’. The definition of ‘privileged’, for these purposes, is that either the effective user ID is zero, or, if POSIX.1e capabilities are supported, that at least one capability is raised in either the Effective or Inheritable capability vectors. |
|-|-|
| %? | The return status of the last command executed just before the prompt. |
| %_ | The status of the parser, i.e. the shell constructs (like ‘if’ and ‘for’) that have been started on the command line. If given an integer number that many strings will be printed; zero or negative or no integer means print as many as there are. This is most useful in prompts PS2 for continuation lines and PS4 for debugging with the XTRACE option; in the latter case it will also work non-interactively. |
| %^ | The status of the parser in reverse. This is the same as ‘%\_’ other than the order of strings. It is often used in RPS2. |
| %d %/ | Current working directory. If an integer follows the ‘%’, it specifies a number of trailing components of the current working directory to show; zero means the whole path. A negative integer specifies leading components, i.e. %-1d specifies the first component. |
| %- | As %d and %/, but if the current working directory starts with $HOME, that part is replaced by a ‘~’. Furthermore, if it has a named directory as its prefix, that part is replaced by a ‘~’ followed by the name of the directory, but only if the result is shorter than the full path; Filename Expansion. |
| %e | Evaluation depth of the current sourced file, shell function, or eval. This is incremented or decremented every time the value of %N is set or reverted to a previous value, respectively. This is most useful for debugging as part of $PS4. |
| %h %! | Current history event number. |
| %i | The line number currently being executed in the script, sourced file, or shell function given by %N. This is most useful for debugging as part of $PS4. |
| %I | The line number currently being executed in the file %x. This is similar to %i, but the line number is always a line number in the file where the code was defined, even if the code is a shell function. |
| %j | The number of jobs. |
| %L | The current value of $SHLVL. |
| %N | The name of the script, sourced file, or shell function that zsh is currently executing, whichever was started most recently. If there is none, this is equivalent to the parameter $0. An integer may follow the ‘%’ to specify a number of trailing path components to show; zero means the full path. A negative integer specifies leading components. |
| %x | The name of the file containing the source code currently being executed. This behaves as %N except that function and eval command names are not shown, instead the file where they were defined. |
| %c %. %C | Trailing component of the current working directory. An integer may follow the ‘ % ’ to get more than one component. Unless ‘ %C ’ is used, tilde contraction is performed first. These are deprecated as   %c   and   %C   are equivalent to   %1~   and   %1/, respectively, while explicit positive integers have the same effect as for the latter two sequences. |

### Date and Time

| Import | Output |
|--------|--------|

### Visual Effects

| Import | Output |
|--------|--------|

## Conditional Substrings in Prompts
