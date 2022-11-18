# The Abstraction: The Process
The process is a simple term that quite literally translates to "A running program". 

Let's think when we are running code, everything is sequential. One function after 
another, but we cannot run all the functions at once simultaneously. However, in an operating system a user would like to do many things at once, maybe browse the
web while listening to music. Which brings the highlight of the problem, how can we make a system that can run hundreds and thousands of processes at the same time?

In the grand scheme of things, a CPU thread is designed to only handle one task. But how can an OS run so many processes while relying on these few threads? 
The OS creates an "illusion" of many CPU threads by "virtualizing" the CPU. There are some cruicial techniques to do this, most notably "Time sharing" and "Space sharing".

Time sharing is the process of allowing resources to be used for some time period by one task, then onto the next task. Sort of like taking turns in sharing the resources 
based on time.

Space sharing is the process of dividing resources porportionally to the tasks that needs it.

Understanding the "machine state" is fundamental to understand all the elements that make up the process. In simpler words, *what parts of the machine* can read/update the process at any given time? For instance, *memory*. The data that uses the memory run in as well as read/write, thus making the memory a part of the process.

## Process API
Think of this as the fundamental "operations" we can do on an OS

- **Create** \: Creating a new process upon entering commands. A good example is opening up a game on your pc, when double clicking your game, the game opens. 
- **Destroy** \: An interface that is able to "destroy" or "terminate" a running program. Notably on windows, you can end a task through the task manager. For instance when your game crashes, you can simply forceably shut it down.
- **Wait** \: Don't know why it's important but basically waiting for a process to stop running.
- **Miscellaneous Control** \: Controls such as suspending a task for a time period and resuming later. For example, disabling anti-cheat for whatever purpose
- **Status** \: An interface that retrieves information about the status of the machine, for example the amount of time a process has been running
