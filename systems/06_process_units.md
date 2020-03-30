## Describing Units
- A single motherboard can have one or more CPUs
- A single CPU can have one or more cores
- A single non-hyperthreaded CPU core can execute a single thread at once
- A single hyperthreaded CPU core can execute two threads at once
- A single process can have one or more threads
- A single program can have one or more processes

### Implications
- A single non-hyperthreaded CPU core can execute one single-threaded process at once
- A single hyperthreaded CPU core can execute two single-threaded processes at once
- A single hyperthreaded CPU core can execute one double-threaded process at once
- Two non-hyperthreaded CPU cores can execute two single-threaded processes at once
- Two non-hyperthreaded CPU cores can execute one double-threaded process at once
- Two hyperthreaded CPU cores can execute four single-threaded processes at once
- Two hyperthreaded CPU cores can execute two double-threaded processes at once
- Two hyperthreaded CPU cores can execute two single-threaded processes and one double-threaded process at once

## An Example using Chrome
- One program
	- Chrome browser
- One program with one or more processes
	- Each Chrome browser tab is a process
- One process with one or more threads from one program:
	- A Chrome tab playing a Youtube video in one thread, another thread spawned for the comments section, and another for a user's login information

## An Example using Word
- If you start MS Word, it is a process
- In MS Word, you type something and it gets automatically saved
- Meaning, we're able to edit something and save something at the same time
- In this case, we have two separate threads for editing and saving
- We've observed editing and saving happening in parallel
- Therefore, we've observed these two threads being executed in parallel

## An Example using Paint
- If you start MS Pain, it is a process
- In Paint, we can draw pictures by reading mouse movements
- The program must give its full attention to the mouse input and draw at the same time
- To do this, two or more threads of a program will execute at the same time

## An Example using the JVM
- A JVM runs in a single process
- Threads in a JVM share the heap belonging to that process
- That is why several threads may access the same object
- Threads share the heap and save their own stack space
- This is how one thread's invocation of a method and its local variables are kept thread safe from other threads
- However, the heap is not thread-safe and must be synchronized for thread safety

## References
- http://www.math-cs.gordon.edu/courses/cs312/lectures/pdf/usingOS.pdf
- https://stackoverflow.com/questions/1050222/what-is-the-difference-between-concurrency-and-parallelism
- https://www.quora.com/What-is-the-difference-between-the-thread-of-a-process-and-the-child-of-a-process-What-are-some-real-time-examples
