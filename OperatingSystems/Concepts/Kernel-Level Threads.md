---
aliases:
  - KLT
  - Kernel Level Threads
---
## **Quick Summary**

Kernel-level threads are threads managed directly by the operating system kernel.

---

## **Core Idea**

* The OS kernel is responsible for creating, scheduling, and managing threads.

---

## **What it is**

**Kernel-Level Threads (KLTs)** are threads that the operating system directly manages.

Unlike user-level threads:

* The kernel is aware of every thread.
* Each thread has a kernel-managed TCB.

Applications must use **system calls** to create and manage threads.

---

## **How its Used**

KLTs allow the OS to:

* Schedule threads individually
* Run threads on multiple CPUs
* Prevent entire processes from blocking when one thread blocks

This improves concurrency and system responsiveness.

---

## **Example**

A server creates multiple kernel threads:
```
Thread 1 → handles user request A
Thread 2 → handles user request B
Thread 3 → handles user request C
```

The kernel scheduler can run these on different CPUs.

---

## **Details**

### Advantages

* True parallelism
* Better handling of blocking operations

### Disadvantages

* Thread creation and switching are slower than ULTs
* Requires kernel interaction

---

## **Related**

* [[User-Level Threads]]
* [[Thread]]
* [[Multithreading]]
* [[Thread Control Block]]

---

## **One Line Recall**

Kernel-level threads are managed and scheduled directly by the operating system kernel.