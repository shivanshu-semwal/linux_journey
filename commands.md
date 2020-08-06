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
^h - erases text (backspace)
^c - send interrrupt signal
^d - terminates the login session (eof cahracter)
^s - stop scrolling the output and lock keyboard
^q - start scrolling and unlock keyboard
^u - kills the line without executing the command
^\ - end the sigkill signal - but creates a core file containing the memory dump of the program
^z - suspends the program and return to the shell
^j - alternative to the enter (carriage return)
^m - alternative to the enter

sitty sane - restotres the terminal
```



