In this file we will see how to limit total CPU usages of a user.

**By using cpulimit and cputool command we can control only the CPU usages of any process. But by this way we cannot restrict
user's overall CPU uses. For example if we apply restriction on one process of a user then user can start another process which
will may consume 100% CPU of our system. So to avoid this we will have to apply restrictions so that total sum of CPU usages of all the processes of user do not exceed over the decided limit( by admin).**

###### For this use the following command
```
sudo systemctl set-property user-1000.slice CPUQuota=50%
```
Here in the above command replace **1000** with **the user id of the user** on which you want to apply restrictions.(Get id by typing *id* in the terminal).
In the above command we are restricting the user of user id **1000** not to use CPU over 50 percent.

**NOTE:** Don't put CPUQuota percentage value so small(for e.g. 1%) because it will slow down your system so much such that it will take you about 15 minutes to type next command. 

To see the changes done by above command see file

```
cat /sys/fs/cgroup/cpu,cpuacct/user.slice/user-1000.slice/cpu.cfs_quota_us
```
Some times above file may not exist but after typing first command it get created automatically


