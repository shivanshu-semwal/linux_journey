# Some basic commands

## man - linux manual 

```txt
man [command] - get help on the command
man [section-number] [command] - get help on the command in the section given by section-number
man -k [keyword] - find the commands which deals with the keyword
man -f [command] - one line help on the command
```

```txt
apropos is same as the man -k command
whatis is same as the man -f command
```

## Control character in the linux terminal 🖥

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

sitty sane - restotres the terminal
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
> 