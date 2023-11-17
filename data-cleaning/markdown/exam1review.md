# Exam 1 Review for Operating Systems Course

## Table of Contents
1. [Textbook Reference](#textbook-reference)
2. [Kernel](#kernel)
3. [Operating System's Role](#operating-systems-role)
4. [Interrupts](#interrupts)
5. [Programs vs Processes](#programs-vs-processes)
6. [Process Creation](#process-creation)
7. [Process Control Block](#process-control-block)
8. [Code Examples](#code-examples)
9. [Kernel Mode vs User Mode](#kernel-mode-vs-user-mode)

---

### Textbook Reference
- **Textbook**: Tanenbaum & Bo, Modern Operating Systems: 4th ed.
- **Copyright**: 2013 Prentice-Hall, Inc.

---

### Kernel
- **Definition**: The part of the OS that implements basic functionality and is always resident in memory.

---

### Operating System's Role
- Provide the user with a cleaner model of the computer.
- Manage resources through an abstracted interface.

---

### Interrupts
- **Definition**: Mechanism used by the OS to signal that a high-priority event has occurred.
- **Examples**: Mouse movements, disk reads.
- **Action**: The controller causing the interrupt places the interrupt number in an interrupt register. The OS must then take action.

#### Interrupt Vector
- **Technique**: Data structure called the interrupt vector.
- **Entries**: One entry for each interrupt, containing the address for the interrupt service routine.

---

### Programs vs Processes
- **Program**: A sequence of instructions written to perform a specified task.
- **Process**: An instance of a program in execution.
- **Difference**: A computer program is a passive collection of instructions; a process is the actual execution of those instructions.

#### Process State Diagram
- Nodes represent process states, and directed edges represent state transitions.

#### Parent and Children PIDs
- `fork` returns the child’s PID to parent processes but returns 0 to the children.
- To determine the parent PID, you can call `getppid()`.

---

### Process Creation
- **After fork()**: Both the parent and child continue executing with the instruction that follows the call to fork().
- **Child gets**: Copy of the parent’s data space, heap, stack, and text segment if it’s read-only.

#### Copy-On-Write
- **Linux Specific**: Parent process's pages are not copied for the child process.
- **Page Fault**: Occurs when either process modifies a page, creating a separate copy for that process.

#### Inherited and Unique Properties
- **Inherited**: user ID, group ID, process group ID, etc.
- **Unique**: the return value from fork(), the process IDs, file locks, etc.

---

### Process Control Block (PCB)
- **Definition**: Data structure maintained by the kernel to keep track of all the process information.
- **Fields**: Over 170+ fields including pointers to other data structures like open files table and page tables.

#### Process Tables
- **Implementation**: Usually an array of pointers to process control block structures.
- **Linux**: Called `task_struct`.

---

### Code Examples
- `fork()` code example: I/O is buffered. Make sure to use `flush()`.
- `waitpid()` code example.
- `exec` code example.

---

### Kernel Mode vs User Mode
- **Privileged Mode**: OS kernel processes can execute all types of hardware operations and access all memory.
- **User Mode**: Cannot execute low-level I/O and is restricted by memory protection.

#### How does the OS track a process?
- **PID**: Each process has a unique process identifier, or PID.
- **Datatype**: The datatype is an opaque type called `pid_t`.

#### Switching Modes
- Processes switch between user space and kernel space using system calls.

---

# Operating Systems Course Notes

## Table of Contents
1. [x86 Protection Rings](#x86-protection-rings)
2. [CPU Rings and Privilege](#cpu-rings-and-privilege)
3. [Address Spaces](#address-spaces)
4. [System Calls](#system-calls)
5. [OS Structures](#os-structures)
6. [Scheduling](#scheduling)
7. [FCFS Scheduling](#fcfs-scheduling)
8. [Time Quantum](#time-quantum)
9. [SJN and SRTF](#sjn-and-srtf)
10. [Lottery Scheduling](#lottery-scheduling)

---

### x86 Protection Rings
- Four privilege levels or rings, numbered from 0 to 3.
  - **Ring 0**: Most privileged
  - **Ring 3**: Least privileged
- Rings 1 and 2 are rarely used in practice.
  - VMs have changed this.

#### Programs and Rings
- Programs in **Ring 0** have full system access.
- Programs in **Ring 3** can fail without affecting the entire system.

---

### CPU Rings and Privilege
- CPU privilege levels are not related to OS user roles (root, admin, guest, etc.).
- All user code runs in **Ring 3**, and all kernel code runs in **Ring 0**.

#### User Mode Limitations
- User mode has restricted access to memory and I/O ports.
- Cannot perform tasks like opening files or sending network packets without kernel intervention.

---

### Address Spaces
- An address space is the set of RAM addresses a process can use.
- 32-bit address space equals 4GB, with the kernel getting the upper 1GB.

---

### System Calls
- Programs use system calls to access OS-controlled resources.
- System calls issue an interrupt instead of directly calling a section of code.
  - This allows the OS to verify privileges.

#### Monolithic Systems
- Basic structure:
  1. Main program invokes the requested service procedure.
  2. Service procedures carry out system calls.
  3. Utility procedures assist service procedures.

---

### OS Structures
#### Microkernel
- Only includes basic functionality in the kernel.
- Everything else runs in user space.

##### Micro vs. Monolithic
- Modules at one level call functions provided by modules at the same or lower level.

---

### Scheduling
- Scheduling algorithms can be divided into two categories:
  - Non-preemptive (cooperative)
  - Preemptive

#### Scheduling Algorithm Goals
- **Batch Systems**: Maximize throughput, minimize turnaround time, and utilize CPU.
- **Interactive Systems**: Minimize response time.
- **Real-time Systems**: Meet deadlines.

---

### FCFS Scheduling
- First Come, First Served (FCFS) algorithm.
- Fair but can be inefficient.

#### Examples
- **Example 1**: Average Waiting Time = 12.67
- **Example 2**: Average Waiting Time = 0.67

---

### Time Quantum
- Choosing the length of the time quantum is challenging.
- Context switching is expensive.

---

### SJN and SRTF
- Shortest Job Next (SJN) and Shortest Remaining Time First (SRTF) algorithms.
- SJN with Preemption: Average Waiting Time = 2.5

---

### Lottery Scheduling
- Processes receive a lottery ticket.
- A ticket is chosen at random to decide which process runs next.

---

**Note**: All information is based on materials © 2015 and © 2017 Trevor Bakker and The University of Texas at Arlington.
