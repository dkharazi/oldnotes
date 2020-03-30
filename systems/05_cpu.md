## General Description
- A CPU is the electronic circuitry within a computer that carries out the instructions of a computer program by performing the following operations
	- Basic arithmetic
	- Logical operations
	- Control operations
	- Input/output (I/O) operations
- A CPU is divided up into three different parts:
	- Control Unit (CU)
	- Arithmetic Logic Unit (ALU)
	- Registers
- A CPU can only understand instructions written as machine code (or machine language)
- A CPU performs these calculations using binary

## Motivating the Control Unit and Registers
- Data is either stored in memory, storage, cache, or registers
- A CPU cache is used by the CPU of a computer to reduce the average cost (i.e. time or energy) to access data from the main memory
- A CPU register is used by the CPU of a computer the reduce the average cost even further
- More specifically, a CPU register is a quickly accessible location available to a CPU and consists of a small amount of fast storage spaces
- Some registers may have specific hardware functions and may be read-only or write-only
- The control units controls the flow of data within the CPU
- Input will come into the CPU via a bus
- Output exits the CPU via a bus

## Architecture of CPU
- ALU: An arithmetic logic unit that executes all calculations within the CPU
- CU: A control unit that coordinates how data moves around
- Registers: A memory location within the actual CPU that allows the CPU to access data very quickly, and can be any of the following:
	- Program Counter: Stores an address of the next and previous instruction in the RAM
	- Memory Address Register: Stores an address of the current instruction being executed
	- Memory Data Register: Stores the data that is to be sent to or fetched from memory
	- Current Instruction Register: Stores the actual instruction that is being decoded and executed
	- Accumulator: Stores result of calculations
- Buses
	- Address Bus: Carries the address of the instruction or data
	- Data Bus: Carries data between the CPU and memory
	- Control Bus: Sends control signals, such as memory read signals or memory write signals

## References
- https://computersciencewiki.org/index.php/Architecture_of_the_central_processing_unit_(CPU)
- http://people.cs.ksu.edu/~schmidt/300s05/Lectures/OSNotes/os.html
