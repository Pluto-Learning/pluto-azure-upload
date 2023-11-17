# CSE 3320 Exam #1 - Spring 2022 (Gry!ndor Version)

## General Instructions

- **Closed Book, Closed Notes**: You may use a hand-written 3x5 note card with notes.
- **Answer Format**: Please answer the questions briefly. Complete sentences are not necessary.
- **Legibility**: Write your answers legibly. Unreadable answers will be counted wrong.
- **Honor Code**: Ensure you uphold the highest standards of integrity.

---

## Questions

### Deadlock Conditions [4pts]

1. List the four conditions required for a deadlock.

### Context Switch [4pts]

2. Define a context switch.

### Kernel Guarding [8pts]

3. How does the kernel on an x86_64 architecture guard kernel space?

### Microkernel vs Monolithic Kernel [8pts]

4. Differentiate between a microkernel and a monolithic kernel. Provide an advantage and disadvantage of each, and give an example of an operating system with each kernel type.

### Operating System Definition [8pts]

5. Define an operating system.

### Data Structures in OS [8pts]

6. What data structure is used by the OS to manage individual process data? How many are there?

### CPU Utilization [8pts]

7. A computer has 64GB of RAM of which the operating system occupies 512 MB. The processes are all 256 MB and have the same characteristics. If the goal is 80% CPU utilization, what is the maximum I/O wait time that can be tolerated with the maximum number of processes running?

### GANTT Chart [8pts]

8. Given the table above, show the GANTT chart for a SJN with Preemption (also known as STRF) scheduler. Mention that the lowest priority value is the highest priority if relevant.

### Average Times [8pts]

9. Calculate the average response time, average wait time, and average turnaround time.

#### Process Table

| Process ID | Arrival Time | Runtime (seconds) | Priority |
|------------|--------------|-------------------|----------|
| 1          | 0            | 2                 | 4        |
| 2          | 0            | 4                 | 2        |
| 3          | 3            | 6                 | 1        |
| 4          | 5            | 6                 | 3        |
| 5          | 8            | 3                 | 1        |
| 6          | 12           | 1                 | 4        |
| 7          | 15           | 5                 | 2        |

### Multitasking [4pts]

10. Define cooperative multitasking and preemptive multitasking. Provide an advantage of each.

### Time Quantum [4pts]

11. What is a time quantum?

### Kernel Definition [8pts]

12. Define a kernel.

### System Call [4pts]

13. What system call is used to create a new process? What are its return values?

### Deadlock Detection [8pts]

14. Is the following deadlocked?

```latex
\[
\text{Existing} = [2,3,4,6], \text{Available} = [0,1,1,2]
\]
\[
\text{Allocated} = 
\begin{pmatrix}
1 & 0 & 2 & 0 \\
0 & 1 & 1 & 1 \\
1 & 1 & 0 & 1 \\
0 & 0 & 0 & 2
\end{pmatrix}
\]
\[
\text{Needed} = 
\begin{pmatrix}
0 & 0 & 0 & 3 \\
1 & 1 & 4 & 4 \\
0 & 0 & 1 & 1 \\
2 & 1 & 3 & 3
\end{pmatrix}
\]
```

### External Fragmentation [8pts]

15. Explain external fragmentation, the solution we discussed for it, and why that solution is not optimal.

---

## Additional Resources

- Powers of 2 table is available on the last page of the exam.

