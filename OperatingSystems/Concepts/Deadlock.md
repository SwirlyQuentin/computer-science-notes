## **Quick Summary**

Deadlock is when processes are stuck waiting on each other forever and none can proceed.

---

## **Core Idea**

* Circular waiting causes the system to halt progress.

---

## **What it is**

A **Deadlock** occurs when two or more processes are blocked indefinitely because each is waiting for a resource held by another.

No process can continue, and the system becomes stuck.

---

## **How its Used**

Deadlocks are not desired but must be handled in operating systems, databases, and multithreaded applications.

Strategies include:

* Prevention
* Avoidance
* Detection and recovery

---

## **Example**
```
Process A holds Resource 1, waiting for Resource 2
Process B holds Resource 2, waiting for Resource 1
→ Neither can proceed
```

---

## **Details**

### Four Necessary Conditions

1. Mutual exclusion
2. Hold and wait
3. No preemption
4. Circular wait

All four must be present for deadlock to occur.

---

## **Related**

* [[Mutual Exclusion]]
* [[Starvation]]
* [[Process Synchronization]]

---

## **One Line Recall**

Deadlock = processes waiting forever on each other.