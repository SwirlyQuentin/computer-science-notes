## **Quick Summary**

Mutual exclusion ensures that only one process can enter a critical section at a time.

---

## **Core Idea**

* Prevent multiple processes from accessing shared resources simultaneously.

---

## **What it is**

**Mutual Exclusion** is a property of a system that guarantees only one process or thread is executing in a critical section at any given time.

It is a fundamental requirement for solving the **critical section problem**.

---

## **How its Used**

Mutual exclusion is implemented using:

* Mutex locks
* Semaphores
* Monitors
* Atomic operations (hardware support)

Used in operating systems, multithreaded programs, and databases.

---

## **Example**
```c
lock(mutex);

// critical section
counter++;

unlock(mutex);
```

Only one process can hold the lock, so only one executes the critical section.

---

## **Details**

**Guarantees**
* Prevents data corruption
* Ensures safe access to shared resources

**Trade-offs**
* Too much locking → performance issues
* Poor design → [[Deadlock]]

---

## **Related**

* [[Critical Section]]
* [[Deadlock]]
* [[Process Synchronization]]

---

## **One Line Recall**

Mutual Exclusion = only one process in the critical section at a time.