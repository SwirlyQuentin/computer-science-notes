---
aliases:
  - CS
---
## **Quick Summary**

A critical section is a part of code that accesses shared data and must only be executed by one process at a time.

---

## **Core Idea**

* Protect shared resources from simultaneous access to prevent inconsistent data.

---

## **What it is**

A **Critical Section** is a segment of code where a process accesses shared data or resources.

If multiple processes enter this section at the same time:

* Data may become **corrupted**
* Results become **unpredictable**

Because of this, only one process should execute a critical section at any given time.

---

## **How its Used**

Critical sections appear whenever shared resources are involved:

* Updating shared variables
* Writing to files
* Accessing databases
* Modifying shared game state

They are protected using synchronization mechanisms like locks (mutexes) and semaphores.

---

## **Example**

### Shared Counter
```c
int counter = 0;

// Critical section
counter = counter + 1;
```

If two processes execute this at the same time:

* Both read `counter = 0`
* Both write `1`

Final value = **1 instead of 2**

---

## **Details**

Without protection leads to [[Race Condition]] and causes inconsistent system behavior.

Key requirement: must enforce [[Mutual Exclusion]].

---

## **Related**

* [[Mutual Exclusion]]
* [[Race Condition]]
* [[Process Synchronization]]

---

## **One Line Recall**

Critical Section = code that must run one process at a time.