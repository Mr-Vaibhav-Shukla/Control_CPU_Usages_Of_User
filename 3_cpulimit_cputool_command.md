# cpulimit
## cpulimit - limits the CPU usage of a process
### SYNOPSIS

```
cpulimit [TARGET] [OPTIONS...] [ -- PROGRAM]
```

### DESCRIPTION

##### TARGET must be exactly one of these:
```
-p, --pid=N
pid of the process

-e, --exe=FILE
name of the executable program file

-P, --path=PATH
absolute path name of the executable program file
```
##### OPTIONS
```
-b, --background
run cpulimit in the background, freeing up the terminal

-f, --foreground
run cpulimit in foreground while waiting for launched process to finish

-c, --cpu
specify the number of CPU cores available. Usually this is detected for us.

-l, --limit=N
percentage of CPU allowed from 1 up. Usually 1 - 100, but can be higher on multi-core CPUs. (mandatory)

-q, --quiet
Runs in quiet mode, avoids writing update messages to console.

-k, --kill
kill target process instead of throttling its CPU usage

-m, --monitor-forks
watch  and  throttle  child  processes  of the target process Warning: It is usually a bad idea to use this flag on a 
shell script. The commands in the script will each spawn a process which will, in turn, spawn more copies of this pro-
gram to throttle them, bogging down the system.

-r, --restore
restore a process killed using the -k flag.

-s, --signal
send an alternative signal to the watched process when we exit. Default is SIGCONT.

-v, --verbose
show control statistics

