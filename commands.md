# Some basic commands

## man - linux manual 

```txt
man [command] - get help on the command
man [section-number] [command] - get help on the command in the section given by section-number
man -k [keyword] - find the commands which deals with the keyword
man -f [command] - one line help on the command
```

```txt
apropos is same as the man -k command - used to find commands associated with a particular keyword
whatis is same as the man -f command - used to ge one line help on a command
```

## Control character in the linux terminal

```txt
^s - stop scrolling the output and lock keyboard
^q - start scrolling and unlock keyboard

^u - kills the line without executing the command

^c - send interrrupt signal
^\ - end the sigkill signal - but creates a core file containing the memory dump of the program
^z - suspends the program and return to the shell

^d - eof cahracter (terminates the login session)
^h - erases text (backspace)
^j - alternative to the enter (carriage return)
^m - alternative to the enter

sitty sane - restores the terminal
```

## General purpose utilities

```txt
cal [ [month] year] -  print the calender of the giver year and month
date - displays current date
date +[symbol] - display the current date particular part given by the symbol
    [d - day] [y - year] [H,M,S - hour, minute, second] [D - date] [T - time]


bc - basic calculator
passwd - change current password
who - show currently logged user
who am i - show your user details

(uname - stands for unix name)
uname - show OS
uname -r - show current realease of the OS
uname -n - show first letter of the domain
uname -a - show every detaill about the system

(tyy - stands for teletype)
tty - tells the filename of terminal you are using

(stty - settings of tty)
stty - displays basic settings
stty -a - displays all tty settings
    >its first line contains speed, rows, columns, lines of the terminal
    >the it shows the settings of the control characters, in form keyword = value
    >rest line contains the keyword or -keywords :: the prefix - implies that the option is turned off

a basic example::

speed 38400 baud; rows 41; columns 159; line = 0;
intr = ^C; quit = ^\; erase = ^?; kill = ^U; eof = ^D; eol = <undef>; eol2 = <undef>; swtch = <undef>; start = ^Q; stop = ^S; susp = ^Z; rprnt = ^R; 
werase = ^W; lnext = ^V; discard = ^O; min = 1; time = 0;
-parenb -parodd -cmspar cs8 -hupcl -cstopb cread -clocal -crtscts
-ignbrk -brkint -ignpar -parmrk -inpck -istrip -inlcr -igncr icrnl -ixon -ixoff -iuclc -ixany -imaxbel iutf8
opost -olcuc -ocrnl onlcr -onocr -onlret -ofill -ofdel nl0 cr0 tab0 bs0 vt0 ff0
isig icanon iexten echo echoe echok -echonl -noflsh -xcase -tostop -echoprt echoctl echoke -flusho -extproc

stty sane - restores default settings
stty -echoe -set the echoe off i.e. now backspace won't erase the characters
stty -echo -sets the keyboard input display off used for passwords
stty intr \^c - sets the interrrupt control character
```

## echo - printing

```txt
echo [text to print]
echo 'text to print as it is'
echo -e "interpret escape characters"
echo "$var" - prints the variable var
```

```txt
\a - bell
\b - backspace
\c - no newline
\f - formfeed
\n - new line
\r - carriage return
\t - tab
\v - vertical tab
\\ - back slash
\0n- ascii charcater represented by octal value n
```

## filesystem 

Everything is file in linux.

```txt
ordinary file - binary/text file
directory file - contains filename and there inode number
device file
```

```txt
pwd - print workling directory

cd - change directory
cd ~ - change to the home directory
cd - - cahnge to previous directory(used for toggeling)

mkdir - make directory
rmdir - remove directory(empty directory)

ls - list files 
options:
-x multicolumnar output
-F mark executables with *, directories with /, symbolic links with @
-a show all files
-R recursive list
-r sort in reverse
-l long listing
-t sort by last modification time
-u sort by last access time
-i display inode number

```

## handling text files

```txt
cat [filename] - displays the contents of the file 
cat -v [filename] - displays the non-graphical characters also
cat -n [filename] - displays the line number also


cp [file] [destination] - copy file to the destination
cp -i - interactive copy(provides warning while overwriring)
cp -R - recursive copy 


mv - renames a files 

rm - remove a file
```

## archiving and compressing

```txt

gzip to compress tar to archive and zip to archive and compress

gzip and gnuzip (.gz)

gzip -d [filename] - decompress the file
gzip -r [filename] - recursive compression
gzip -l [filename] - list the compression ratio

tar - archival program (.tar file)

tar
-c create an archive
-x extract the archive
-t view the archive
-x extract the files form archive
-t displays files in archive
-f arch - specifies the archive arch
-v verbose mode

tar -cvf [archive name] [files to add...]

now to compress the file use gzip
gzip [archive name] - creates a tar-gzipped file

tar -xvf [archive name] - extracts the archive
tar -tvf [archive name] - view the archive


Doing archiving and compression together (-z)

tar -cvzf [compressed archive] - create a compressed archive

zip AND unzip - compressing and archiving together (.zip)

zip [archive name] [input files] - creates an archive
zip -r [archive name] - recursive compressing
unzip [archive name] - unzips an archive
unzip -v [archive name] - viewing detaill about the compressed file
```

## Basic File Attributes

```txt

ls -l - long listing files 
The columns are as folows::
> File Type and Permissions
> Links - the number of links associated with that particular file
> Ownership - owner of the file
> Group Ownership 
> File Size in bytes
> Last Modification Date
> Filename
```

```txt
File Ownership
> The user-id (UID) 
> The group-id (GID)

id - view UID and GID associated with particular user
```

```txt
File Permissions

 0 1 2 3 4 5 6 7 8 9
|d|r|w|x|r|w|x|r|w|x|

r - read permission
w - write permission
x - execute permission

0 - defines the type of file d for directory, - for normal file
1,2,3 - permission granted to owner of file
4,5,6 - permission granted to group owner of file
7,8,9 - permission granted to other users

chmod - used to change the permissions of the file

chmod [category][operation][permission] [filename...]

category - u-user, g-group, o-other, a-all(ugo)
operation - + assign permission, - remove permission, = absolute permission
permission - r, w, x

chmod [ocatal-code] [filename...] - used to assign absolute permission

        a        b        c
|0|  |4 2 1|  |4 2 1|  |4 2 1|
|d|  |r|w|x|  |r|w|x|  |r|w|x|

octal-code - a three digit code for permission of the file
```

```txt
How directory permission affect the file permissions:
> if the directory has write permission for all than they can delete the files in the directory
```

```txt
Changing file ownership

chown [options] [owner] [files...] - change owner of file to owner
chgrp [group] [files...] - change group of file to group
```

## Shell

```txt
Shell interpretive cycle:
> shell issue prompt and wait for you to enter command
> after a command is entered, the shell scans for the metacharacters and expands abbreviations 
> the shell waits for the command to execute

Types of shell:
> The Bourne family comprising the Bourne shell (/bin/sh) and its derivatives - the Korn shell (/bin/ksh) and Bash (/bin/bash).
> the C shell (/bin/csh) and its derivative, Tcsh (/bin/tcsh)
```

```txt
Wildcard Meaning
*		Any Number of characters including none
?		A single character
[ijk]	A single character- either i, j, or k
[x-z]	A single character within the ASCII range of character x and z
[!ijk]	A single character that is not i, j, k
[!x-z]	A single character not in the ASCII range of character x and z
{pat1, pat2, ...}	pat1, pat2, ...
```

```txt
Redirection
* 0-Standard Input - The file (or stream) representing input, connected to the keyboard.
* 1-Standard Output - The file (or stream) representing output, connected to the display.
* 2-Standard Error - The file(or stream) representing error, connected to display.

Three standard file are represented by a number called file descriptor. 1,2,3.

< - file redirection i.e. taking contents of one file as input
| - pipe i.e. giving output of one command to another

taking input from both file and standard input::
cat ~ foo       #first from standard input and then from foo
cat foo ~ bar   #first from foo, the stdin then bar

> - redirecting output to a file
>> - appending output to a file

File descriptors are implictily prefixed to the redirection symbols.
e.g. > is same as 1>, < is same as <0.

2> - redirecting error stream
2>> - appending error stream
```

