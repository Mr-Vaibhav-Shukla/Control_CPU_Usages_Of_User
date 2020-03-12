Before we start learning how to control the CPU usages of a user we will have to understand some commands. 
Commands are:
## man
It is the command which helps in getting the detailed information of any command.

**For e.g.**
```
man man
```
Above command will give the detailed information of man command.

----

## top/htop
### top - display Linux processes
The top program provides a dynamic real-time view of a running system. It can display system summary information as well as a list of processes or threads currently being managed by the Linux kernel. The types of system summary information shown and the types, order and size of information displayed for processes are all user configurable and that configuration can be made persistent across restarts.

**To display all Linux processes type given command in the terminal**
```
top
```
### htop - interactive process viewer
It is similar to top, but allows you to scroll vertically and horizontally, so you can see all the processes running on the system, along with their full command lines, as well as viewing them as a process tree, selecting multiple processes and acting on them all at once.
Tasks related to processes (killing, renicing) can be done without entering their PIDs.

**And to display all Linux processes type given command in the terminal**
```
htop
```

----

## watch
Watch runs command repeatedly, displaying its output and errors (the first screenfull). This allows you to watch the program output change over time.  By default, command is run every 2 seconds and watch will run until interrupted.
*use man command for more details*

----

## who/w

### who - show who is logged on
This command prints the information about the user who are currently logged in.

### w - show who is logged on and what they are doing.
w displays information about the users currently on the machine, and their processes.  The header shows, in this order, the current time, how long the system has been running, how many users are currently logged on, and the system load averages for the past 1, 5, and 15 minutes.

*Use* **man** *command for their more details.*

----









