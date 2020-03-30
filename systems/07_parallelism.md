## Parallelism and Concurrency
- Concurrency is a condition that exists when two threads are making progress during a period of time on a system
- Parallelism is a condition that exists when two threads are executing simultaneously during a particular point in time on a system
- Concurrency is a property of a program or system
- Parallelism is a property of the run-time behavior of executing multiple tasks at the same time
- Time-Slicing by the operating system is an example of concurrency
- Simultaneously executing two different threads on a multicore processor is an example of parallelism

## A Conceptual Understanding of a Process
- The process model is based on two independent concepts:
1. Resource grouping
	- We can think of a process as something that groups related resources together
	- Specifically, a process has the following:
		- An address space containing program text and data
		- Information about open files
		- Information about child processes
		- And other resources
2. Execution
	- Or, we can roughly think of a process as a thread of execution
	- A process doesn't perfectly translate to a thread, but we can think of it that way for now
	- A thread of execution is typically referred to as a thread
	- Specifically, a thread has the following:
		- A program counter that keeps track of which instruction to execute next
		- Registers that hold its current working variables
		- A stack that contains the execution history

## Intuition behind Threads and Processes
- A process refers to a program that is being executed
- A child process is a process created by another process (i.e. the parent process)
- A thread is the basic unit to which the operating system allocates processor time
- A thread can execute any code from the process
- Once a process is created by the operating system, a single thread will be initialized within that process, called the primary thread
- Each process can create additional threads from any of its threads
- A major difference between a thread and a process is the following:
	- A process runs in a seperate memory space (compared to other processes)
	- A thread runs in a shared memory space (compared to other threads of the same process)
- Essentially, processes are used to group resources together, whereas threads are the entities scheduled for execution on the CPU

## Motivating Hyperthreading
- Classically, each CPU core could only support a single thread of execution
	- By doing this, the thread's state is maintained via a single program counter and set of registers
- However, it can take a long time to fetch data from the main memory, if the requested data isn't in the cache
- And, while data is being fetched from the main memory, the CPU is just sitting there idle
- So, someone had the idea to have two sets of thread states (PC + registers) so that another thread (maybe in the same process, maybe in a different process) can get work done while the other thread is waiting on the main memory
- This idea of modifying a CPU core to include an extra set of registers and program counter for another thread is called hyperthreading
- Hyperthreaded CPU cores *genuinely* support 2 threads per core, compared to only 1 thread per core for non-hyperthreaded CPU cores

## Motivating Multithreading
- A program can be made up of a single process or multiple processes (i.e. opening new tabs in chrome)
- To make things easier, we typically think of a process as a single program being executed on our computer
- A process is made up of one or more threads
- CPU cores don't execute processes, they execute threads
- A single non-hyperthreaded CPU core can only run one thread
- A single hyperthreaded CPU core can run two threads
- There are only two ways to run threads in parallel:
	1. Ensuring our CPU core is hyperthreaded
	2. Adding CPU cores to our system
		- We can do this by adding more CPU cores to a single CPU (i.e multicore processor)
		- Or by adding more CPUs to our system (i.e Multiprocessor)
- The operating system schedules each thread to be executed on a particular CPU core
	- The operating system is very efficient at scheduling these threads
	- It slices each thread in chunks in an attempt to fairly distribute CPU execution time across threads waiting to be finished executing
- If we're writing a program in some programming language, then that program will create one process with one thread by default when that program is executed
- However, certain programming languages allow us to manually program and manage our own threads
	- Scheduling is still done by the operating system, but we're able to organize code into individual threads and tell our program what to do with those threads once they're executed

## Describing Multithreading
- The idea of a programming language supporting the ability for us to program and manage our own threads is called multithreading
- Java and C++ are some examples of programming languages that support multithreading
- Python does not support multithreading
- Typically, the purpose of a multithreaded program is to execute our code in parallel
- Therefore, multithreading is limited by our hardware capabilities, since our hardware is what provides us with the capability of processing threads in parallel
- If we only have one CPU with one core, then multithreading will not achieve anything
- If we have multiple CPU cores, then multithreading will achieve parallelism

## Parallelism
- A CPU is able to run in parallel if hyperthreading or multicore (hardware level)
- A CPU only appears to run in parallel (but not actually) for multithreaded applications (software level) because the OS by default has very efficient time-slicing or scheduling, where each thread gets a few milliseconds to execute before the OS schedules another thread to run on that CPU core
- Therefore, if we have a java program that starts 4 threads, and have 4 or more cores, then there's a good chance those 4 java threads will run truly in parallel on 4 separate cores, if the cores are idle

## References
- https://stackoverflow.com/a/5593432
- https://stackoverflow.com/a/5593389
- https://stackoverflow.com/a/19518207
- https://stackoverflow.com/a/200543
- https://stackoverflow.com/a/200475
- https://stackoverflow.com/a/49841764
