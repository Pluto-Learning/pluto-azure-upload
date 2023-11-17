# CSE 3320 Exam #2 - Fall 2019

## General Instructions

- **Closed Book, Closed Notes**: You may use a hand-written 3x5 note card with notes.
- **Answer Format**: Brief answers are acceptable. Complete sentences are not necessary.
- **Legibility**: Write your answers legibly. Unreadable answers will be counted as wrong.
- **Honor Code**: You must certify that the work is your own and uphold the spirit of the Honor Code.

---

## Questions

### 1. Page Request Reference String [8pts]

Given a page request reference string of `B D C A B C D E F A B D A B` and a page table size of three, calculate how many page faults will occur with the optimal page replacement algorithm and LRU.

### 2. File System with Inodes [9pts]

Given a file system that uses inodes to represent files. Disk blocks are 2KB in size, and 16-bit pointers. This file system’s index nodes have 14 direct disk blocks, 2 indirect disk blocks, 2 double indirect blocks, and a triple indirect block. What is the largest file that can be held using this inode layout?

### 3. LFU Page Replacement Algorithm [6pts]

Give a downside to the LFU page replacement algorithm.

### 4. FAT32 File Allocation [9pts]

The FAT32 file is a variation of which of the three allocations schemes we discussed? Give an advantage and a disadvantage of FAT32.

### 5. TLB Types [6pts]

You are given a choice of two TLB. Type A executes lookups parallel and has a memory access time of 170ns and a TLB lookup time of 30ns with a 65% hit rate. Type B executes lookups serially and has a memory access time of 170ns and a TLB lookup time of 30ns with a 75% hit rate. From a purely performance perspective, which TLB should you choose? Quantify why.

### 6. Physical and Logical Journals [6pts]

Explain physical and logical journals.

### 7. Addressable Virtual Memory [8pts]

Given 1 GB of physical RAM split into \(2^{16}\) frames and a 32-bit system, what is the maximum addressable virtual memory?

### 8. Demand Paging [8pts]

Explain how demand paging works, its benefits, and negative consequences. How does the sliding window tie into the concept?

### 9. Memory Hole Allocation [8pts]

Given a swapping system in which memory consists of the following hole sizes in memory order: 20 MB, 4 MB, 10 MB, 7 MB, 18 MB, 9MB, 12 MB, and 15MB. Which hole is taken for successive requests of: 12 MB, 10 MB, 8MB, 4MB, 13MB. Give your answer for first fit, best fit, worst fit, and next fit.

### 10. Address Space [8pts]

A computer provides each process with 65,536 bytes of address space divided into pages of 4096 bytes each. A particular program has a text size of 32,768 bytes, a data size of 16,386 bytes, and a stack size of 15,870 bytes. Will this program fit in the machine’s address space in a non-demand paging solution? If the page size were 512 bytes, would it then fit?

### 11. Virtual Addresses [6pts]

For each of the following decimal virtual addresses, compute the virtual page number and offset for a 4-KB page and for an 8 KB page: 20000, 32768, 60000.

### 12. Corrupted Data Block [6pts]

Describe the effects of a corrupted data block for a given file for: 
- (a) contiguous
- (b) linked
- (c) indexed

### 13. Types of Binding [5pts]

List and describe the 5 types of binding we discussed.

### 14. Multilevel Page Table [7pts]

Suppose that a machine has 38-bit virtual addresses and 32-bit physical addresses.
- (a) What is the main advantage of a multilevel page table over a single-level one?
- (b) With a two-level page table, 16-KB pages, and 4-byte entries, how many bits should be allocated for the top-level page table field and how many for the next-level page table field? Explain.

---

## Powers of 2 Table

| Power | Value       |
|-------|-------------|
| 0     | 1           |
| 1     | 2           |
| 2     | 4           |
| 3     | 8           |
| 4     | 16          |
| 5     | 32          |
| 6     | 64          |
| 7     | 128         |
| 8     | 256         |
| 9     | 512         |
| 10    | 1,024       |
| 11    | 2,048       |
| 12    | 4,096       |
| 13    | 8,192       |
| 14    | 16,384      |
| 15    | 32,768      |
| 16    | 65,536      |
| 17    | 131,072     |
| 18    | 262,144     |
| 19    | 524,288     |
| 20    | 1,048,576   |
| 21    | 2,097,152   |
| 22    | 4,194,304   |
| 23    | 8,388,608   |
| 24    | 16,777,216  |
| 25    | 33,554,432  |
| 26    | 67,108,864  |
| 27    | 134,217,728 |
| 28    | 268,435,456 |
| 29    | 536,870,912 |
| 30    | 1,073,741,824 |
| 31    | 2,147,483,648 |
| 32    | 4,294,967,296 |
