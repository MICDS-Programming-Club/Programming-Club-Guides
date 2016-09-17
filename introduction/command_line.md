# The Command Line
If you've done a little bit of research into how websites and databases are ran, you might have encountered something called the *command line*. In this guide, you will learn what it is and how to use it.

## What is this thing?
Generally, the command line is just a prompt that you type *commands* into, and the computer runs those commands. These commands can vary from simply echoing something to the screen to backing up full production databases.

However, the syntax of these commands vary from operating system to operating system. In this guide we will be covering the two most-used ones: Windows and Bash (Unix/Linux).

### What are these dollar signs?
Generally, dollar signs are used to represent an interactive prompt. You'll see these in command examples just about everywhere.

For example:  
```
$ test-command
$ python test.py
$ node who-cares.js
```

## Similarities
There are a couple similarities between the different shells.

### Changing Directories
Generally, to change the current directory, use the `cd` command.

For example:  
```
$ cd cool-directory
```

#### Periods
A single period `.` generally represents the current directory. Two periods `..` generally represent the directory above the current directory.

### Echoing
Generally, to echo something to the screen, use the `echo` command.

For example:  
```
$ echo programming is cool
programming is cool
$ echo i know, right?
i know, right?
```

## Windows Command Line
The Windows command line is not really used all that often for programming, but some servers do use it, and it's probably the easiest way to get experience with a command line.

### Basic Syntax

#### Variables
In Windows command line, variables are created with the `set` command and are called with `%`percent signs`%` surrounding them.  
Strings do not have to be contained within any sort of quotes or delimiters.

For example:  
```
$ set TEST=i love programming club
$ echo %TEST%
i love programming club
```

#### Directory Listings
In Windows command line, to list the contents of the current directory, use the `dir` command. However, this prints a lot of (usually unnecessary) information, so just add the `/b` flag to truncate it to just the files/folders.

For example:  
```
$ dir
09/16/2016 	02:02 PM 	<DIR>  	    .
09/16/2016 	02:02 PM 	<DIR>  	    ..
09/16/2016 	02:02 PM 	<DIR>  	    Programming-Club
04/20/2016  06:09 AM 		  4,332 windows-cmd-line-is-cool.txt
$ dir /b
Programming-Club
windows-cmd-line-is-cool.txt		 
```

**More stuff to come!**

## Bash Command Line
The Bash command line is the most commonly used command line within programming and computers in general. Most servers run a [Linux](https://www.linux.com/what-is-linux) distribution of some sort, usually [Ubuntu](http://www.ubuntu.com/), which all use Bash.

### Basic Syntax

#### Variables
In Bash, variables have no explicit definition command. They are called with a `$`dollar sign in front of them.  
However, as opposed to Windows, strings must be contained within `'`quotes`'`. (Double quotes have a special meaning in Bash. We'll get to that!)

For example:  
```
$ TEST="i love programming club"
$ echo $TEST
i love programming club
```

#### Directory Listings
In Bash, to list the contents of the current directory, use the `ls` command. However, this does not contain hidden files/folders (which are prefixed with a `.`period). To show those, add the `-a` flag to the command.

For example:  
```
$ ls
Programming-Club 	bash-cmd-line-is-cool.txt
$ ls -a
. 	.. 	 Programming-Club 	 .hiddenfile 	bash-cmd-line-is-cool.txt
```

**More stuff to come!**