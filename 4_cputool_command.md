# cputool
## cputool - It is a utility which manages the CPU usages and system load.

### SYNOPSIS
```
cputool [--cpu-limit PCNT]  [--load-limit LOAD]  [ [--pid PID  | --pid-pgrp PID ]  | [--]  COMMAND ... ]
```
### DESCRIPTION
Limit  the  CPU usage of a process or a process group to a given limit and/or suspend processes if the system load exceeds a
threshold. CPUTool works by sending SIGSTOP and SIGCONT signals to processes depending on the system load.

##### OPTIONS
These programs follow the usual GNU command line syntax, with long options starting with two dashes ('-').

A summary of options is included below.
```
 -c, --cpu-limit PCNT
```
Specify the maxium CPU the process / process group can use. Expressed as percentage of total CPU. Eg. 200 is two full CPUs 
in a multi processor system. Specify an integer value.

```
-l, --load-limit LOAD
```
Specify the maxium load the system may experience for the process process group to continue running. Specifyng a fractional
value is possible (e.g. 3.5).

```
-p, --pid PID
```
Manage the CPU usage of a specific PID. This is the most efficient use of CPUTool as it does not have to walk the process
tree to look for forks of children.

```
-P, --pid-pgrp PID
```
Manage the CPU usage of a specific PID's entire process group. The same can be achieved by specifying a COMMAND which CPUTool
will then execute and manage the process group  created by that command.

```
-v, --verbose
```
Increase the amount of messages printed to stderr.

```
-vv
```
will additionally show statistical information.

```
 -vvv
 ```
 will addditionally show signals being sent to processes.
```
 -V, --version
```
Output version information and exit.

```
-h, --help
```
Display a help page and exit.


### NOTES
CPUTool will run on 32-bit and 64-bit Linux systems. It depends on the /proc pseudo-filesystem to detect PIDs and their
resource usage.
TCP network connections could time out if a process is suspended for extended periods of time (while the load is too high).  Not all programs handle this case well.

### EXAMPLES
```
cputool -p 4711 -c 75
```       
Limit the PID 4711 to 75% use of one CPU core.
```
cputool -l 7.5 -- rsync -av /home /backup/`date +%Y-%m-%d`/
```
Run rsync for a local backup only when the system load does not exceed 7.5. See the note for -l when using program that relies on TCP network connections.
