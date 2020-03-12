# What is /etc/security/limits.conf file?

UNIX/Linux operating systems have the ability to limit the amount of various system resources available to a user process. These limitations include how many files a process can have open, how large of a file the user can create, and how much memory can be used by the different components of the process such as the stack, data and text segments.

## Inside the limit.conf file

Inside the limit.conf file each line describe a limit for a user

**where:**

---
### [domain] can be:
* a user name
* a group name, with @group syntax
* the wildcard *, for default entry
* the wildcard %, can be also used with %group syntax,
                 for maxlogin limit
---
### [type] have two values:
* **hard:** for enforcing soft limits
* **soft:** for enforcing hard limits
---
    
### [item] can be of the following

* **core** - limits the core file size (KB)
* **data** - max data size (KB)
* **fsize** - maximum filesize (KB)
* **memlock** - max locked-in-memory address space (KB)
* **nofile** - max number of open file descriptors
* **rss** - max resident set size (KB)
* **stack** - max stack size (KB)
* **cpu** - max CPU time (MIN)
* **nproc** - max number of processes
* **as** - address space limit (KB)
* **maxlogins** - max number of logins for this user
* **maxsyslogins** - max number of logins on the system
* **priority** - the priority to run user process with
* **locks** - max number of file locks the user can hold
* **sigpending** - max number of pending signals
* **msgqueue** - max memory used by POSIX message queues (bytes)
* **nice** - max nice priority allowed to raise to values: [-20, 19]
* **rtprio** - max realtime priority
* **chroot** - change root to directory (Debian-specific)
---
### [values] 
    
*Values are the integer values given to adjust the limit*
    
---
    
#### Note:

* To do changes in limit.conf file you should have to switch to root user or use sudo.

* After performing the changes, exit and re-login from the terminal for the change to take effect.

---    
#### More details can be found from below command on the terminal:
```
    man limits.conf
```

