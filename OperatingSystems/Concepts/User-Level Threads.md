---
aliases:
  - User Level Threads
  - ULT
---
## **Quick Summary**

User-level threads are threads managed entirely by a user program rather than the operating system.

---

## **Core Idea**

* Thread management occurs inside the application using a thread library.

---

## **What it is**

**User-Level Threads (ULTs)** are implemented within the application rather than inside the operating system kernel.

A **thread library** manages these threads and provides functions for:

* Creating threads
* Destroying threads
* Scheduling threads
* Synchronizing threads

The OS kernel is **not aware of these threads** and treats the process as a single-threaded program.

All thread control blocks are maintained within the user process.

---

## **How its Used**

ULTs are used when:

* Fast thread management is needed
* Portability across operating systems is desired

Since they do not require kernel interaction, operations like thread creation and context switching can be very fast.

---

## **Example**

Thread library creates threads:
```
thread_create(taskA)
thread_create(taskB)
thread_create(taskC)
```

The OS sees only **one process**, while the application internally schedules these threads.

---

## **Details**

### Advantages

* Faster thread management
* Portable across operating systems

### Disadvantages

* If one thread blocks, the **entire process blocks**
* Cannot use multiple CPUs effectively

---

## **Related**

* [[Kernel-Level Threads]]
* [[Thread]]
* [[Thread Control Block]]
* [[Multithreading]]

---

## **One Line Recall**

User-level threads are managed by a thread library without kernel involvement.