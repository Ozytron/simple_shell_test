 simple UNIX command interpreter that provides a user interface to access and give orders to the operating system.

Table of Contents
Description
File Structure
Requirements
Installation
Usage
Example of Use
Bugs
Authors
Description
This is a command line interpreter, or shell, in the tradition of the first Unix shell written by Ken Thompson in 1971. This was made as a project for ALX School. In this project we apply the knowledge that we have learned in C programming language. Standard functions and system calls employed in simple_shell include:

access, execve, exit, fork, free, malloc, read, signal, wait, write.
File Structure
AUTHORS - List of contributors to this repository
man_1_simple_shell - Manual page for the simple_shell
shell.h - program header file
shell.c - main function of the shell
main - the main function of the program
ret - return function
extstatus - return status
writeexe - writes to standar error
writes0 - writes to standar error
Requirements
simple_shell is designed to run in the Ubuntu 20.04 LTS linux environment and to be compiled using the GNU compiler collection v. gcc 4.8.4 with flags-Wall, -Werror, -Wextra, and -pedantic.

Installation
Clone this repository: git clone "git@github.com:Ozytron/simple_shell.git"
Change directories into the repository: cd simple_shell
Compile: gcc -Wall -Werror -Wextra -pedantic *.c -o hsh
Run the shell in interactive mode: ./hsh
Or run the shell in non-interactive mode: example echo "pwd" | ./hsh
Usage
The simple_shell is designed to execute commands in a similar manner to sh, however with more limited functionality. The development of this shell is ongoing. The below features will be checked as they become available (see man page for complete information on usage):

Features
 uses the PATH
 implements builtins
 handles command line arguments
 custom strtok function
 uses exit status
 shell continues upon Crtl+C (^C)
 handles comments (#)
 handles ;
 custom getline type function
 handles && and ||
 aliases
 variable replacement
Built-ins
 exit
 env
 setenv
 unsetenv
 cd
 help
 history
Examples
Absolute path commands
non interactive
$ echo "/bin/pwd" | ./hsh
$ /home/timex/simple_shell
interactive mode
$ ./hsh
./hsh$ /bin/echo hello world
helo world
./hsh$ exit
$
short command
non interactive
$ echo "pwd" | ./hsh
$ /home/timex/simple_shell
interactive mode
$ ./hsh
./hsh$ echo hello world
helo world
./hsh$ exit
$
built-ins
non interactive
$ echo "exit" | ./hsh
$ echo $?
0
interactive mode
$ ./hsh
./hsh$ exit 98
$ echo $?
98
Some error output

$ ./hsh
./hsh$ ls /non_existing_folder
ls: cannot access '/non_existing_folder': No such file or directory
./hsh$ exit
$ echo $?
2
$ echo "non_valid_command" | ./hsh
./hsh: 1: non_valid_command: not found
$ echo $?
127
Project files
File	Description
AUTHORS	File with names of the owners and authors of this project
README.md	Nutshell description of simple_shell project
chain.c	Auxiliar functions
signal_exit: handler for SIGINT signals
_calloc: allocate memory and fills it with zeros
built-ins.c	Built-ins functions:
check_word: evalute alpha chars in string
exit_built_in: stop execution of shell
env_built_in: prints environment variables
core_funs.c	Heart of simple_shell
check_builtin: check if first argument is a built-int
not_found_error: handler for print error when command is not found
simple_exec: decision flow for command execution
path_funs.c	Function to check command in path
_getenv: search variable in environment vars
cmd_path: concat first argument with PATH dirs
shell.h	Header file
All includes
All prototypes
Definition of struct params
simple_shell.c	Initialize the simple_shell execution:
test:
Remove \n last char readed with getline
Tokenize and save in argv all arguments readed
Calls simple_exec
main:
Initialize params struct vars
Set signal listenes
Print prompt (interactive mode)
Read arguments with getline
Handle CTRL + D to stop execution
string_function.c	First string functions file
_strcat: concat string (no malloc)
_strlen: get length of string
rev_string: reverse a string
_itoa: convert int to string
_strcmp: compare two strings
string_function2.c	Second string functions file
_strchr: search char in string
string_function3: copy string in other one
str_concat: concat string (malloc)
_atoi: convert string num, to int

others: The description and purpose of other functions which are not listed under project files, but exists under the repository can be found in in the commit messages of the concerned files/functions.	
Full documentation
For more info about this project you can run the man page:

$ ./man_1_simple_shell

Bugs
At this time, there are no known bugs.

Authors
Emmanuel Ozioko Ozytron

Victor mbachu emekambachu
