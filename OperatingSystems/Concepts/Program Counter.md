---
aliases:
  - pc
  - Program Counter (pc)
---

## **Quick Summary**

The program counter (PC) is a CPU register that stores the memory address of the next instruction to execute.

---

## **Core Idea**

* The program counter tracks where a [[thread]] is currently executing in a program.

---

## **What it is**

The **Program Counter (PC)** is a special CPU register that contains the address of the next instruction to be executed.

During program execution:

1. The CPU fetches the instruction at the PC.
2. The instruction is executed.
3. The PC is updated to point to the next instruction.

In a **single-threaded process**, there is only one program counter.

In a **multithreaded process**:

* Each thread has its own **private program counter**
* Each thread progresses independently through the program.

The PC is part of the **CPU state** stored in process or thread control structures.

---

## **How its Used**

The PC is essential for:

* Tracking execution progress
* Supporting context switching
* Allowing multiple threads to run concurrently

When a thread is paused, its program counter value is saved in its **[[Thread Control Block]]**. When resumed, the PC is restored so execution continues from the same instruction.

---

## **Example**

### Simple Instruction Sequence
```
100: load A
104: add B
108: store C
```

Execution flow:
```
PC = 100 → execute load A
PC = 104 → execute add B
PC = 108 → execute store C
```

### [[Multithreading]] Example
```
Thread 1: PC = 240
Thread 2: PC = 820
```

Each thread executes a different part of the program.

---

## **Details**

### Control Flow Changes

The PC changes during:

* Function calls
* Branch instructions
* Interrupts

### Context Switching

During a context switch:

* The PC is saved
* Another thread's PC is restored

---

## **Related**

* [[Thread]]
* [[Thread Control Block]]
* [[Execution Stack]]
* [[Process Control Block]]

---

## **One Line Recall**

The program counter stores the address of the next instruction a thread will execute.