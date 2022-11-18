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

To understand 
