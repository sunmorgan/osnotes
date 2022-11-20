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

When the OS is running a program, they would first load its code into memory(The address space of the progress). Something to note, is that all programs are initially stored in the hardware(hardrives/SSD), the job of the OS is to read the data of bytes and place them in memory. Refer to the picture below:

<img width="717" alt="image" src="https://user-images.githubusercontent.com/64807003/202829419-55e989c9-c791-4860-b4e5-ef3d62bd7a79.png">

The OS then allocates some memory for the run-time stack and gives it to the process. The OS could potentially allocate some memory for the *heap*, which 
is used for dynamically-allocated data(think hashmaps, arraylists)

The OS will also fullfill on initialization tasks, in which refers to I/Os.

## Process States
This simply means the *state* of a process at a given time. It is generally specified into 3 statuses\:
- Running\: This says a process is running on a processor, meaning that it is executing instructions
- Ready\: This says a process is ready to be executed, but the OS decides to not run it at the moment
- Blocked\: This says a process has done some operation such that it is not able to run until some arbitrary event takes place

<img width="502" alt="image" src="https://user-images.githubusercontent.com/64807003/202863997-ea5b4737-535e-4ca3-ac0b-69251701cf8d.png">
In the diagram, the running and ready state are interchangable. In simpler terms, moving a process from ready to running means the process has been scheduled; while moving a process from running to ready means the process has been descheduled.

## Data Structure
An OS usually have a data structure that encapsulates important information, for example, a *process list*. The OS would use it to track the state of each process.
