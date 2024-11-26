# Piping in Linux

Connect commands together in Linux to create powerful pipelines. Each program is its own entity.

## Standard Streams

- **Standard Input (stdin)**: By default, connected to the keyboard. It can be redirected to read from other sources.
- **Standard Output (stdout)**: By default, connected to the terminal screen. It can be redirected to other destinations.
- **Standard Error (stderr)**: By default, connected to the terminal screen. It can be redirected to other destinations.

## Redirection

- **Standard Input (0)**: `cat < input.txt`
- **Standard Output (1)**: `command > output.txt` (truncates before writing)
- **Append Output**: `command >> output.txt` (appends without truncating)
- **Standard Error (2)**: `command 2> error.txt`

Redirection is useful for managing output and error messages, such as keeping track of error messages from web servers.

## Piping

By connecting outputs to inputs, you create pipelines in Linux. There are two ways to get data into a command and two ways to get output from a command.

## Useful Commands

- `tty`: Tells where a terminal is located in Linux.

date | cut --delimiter " " fields 1 here | this is the pipe symbol it pipes the data from the date command to cut commnad 

using tee command can make a junction in the pipe to move data to two places i.e a file and to another command eg | tee fulldate.txt | it takes a snapshot before redirecting the data in two directions

xargs allows to convert pipelined data into command line args for commands that only accept the args and not standard input data eg date | xargs echo  note echo process it own command line arg first before the xargs

using aliases for pipe comands .bash_aliases 
alias <name of alias> = '<piped command>'