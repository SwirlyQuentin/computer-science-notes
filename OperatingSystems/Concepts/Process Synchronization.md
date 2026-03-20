## **Quick Summary**

Process synchronization coordinates processes to safely share data and resources.

---

## **Core Idea**

* Ensure correct execution order and safe resource access.

---

## **What it is**

**Process Synchronization** is the coordination of concurrent processes so that shared data is accessed safely and system behavior remains correct.

It ensures:

* No race conditions
* No data corruption
* Fair access to resources

---

## **How its Used**

Used in operating systems, multithreaded programs, databases, and producer–consumer systems.

Implemented using:

* Mutexes
* Semaphores
* Condition variables

---

## **Example**

### Producer–Consumer

* Producer creates data
* Consumer waits for data
* Synchronization ensures:
  * Producer doesn't overwrite data too early
  * Consumer doesn't read empty data

---

## **Details**

### In Lecture

* Variables `c1`, `c2`, and `will_wait` coordinate access
* Ensures mutual exclusion, no deadlock, and no starvation

### Goals

* Safety (correct results)
* Liveness (progress is made)
* Fairness

---

## **Related**

* [[Critical Section]]
* [[Mutual Exclusion]]
* [[Race Condition]]
* [[Deadlock]]

---

## **One Line Recall**

Process Synchronization = coordinating processes to safely share resources.