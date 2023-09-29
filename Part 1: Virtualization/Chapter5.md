# Process API

Processes are tasks that are running in the operating system, unsurprisingly, each task is unique frokm one another; and they are identified by the PID (process ID). 

There are 3 system calls that are quite important when it comes to process management. 

fork(), it creates a new process. The creator is the parent and the created is the child. 

wait(), is where the parent wait for the child process to finish first before starting, this makes the process *deterministic*, where we know how the processes will act. 

exec(), is where it allows the child to break free from its parent and execute it as if it were a separate program. 

Process controls are available to different users, and normally each user can only control their own process. However, the superuser, known as the *root*, can control the whole system, including other users (think about securuity)