## **Quick Summary**

A race condition occurs when the outcome depends on the timing or order of execution between processes.

---

## **Core Idea**

* Uncontrolled concurrent access leads to unpredictable results.

---

## **What it is**

A **Race Condition** happens when multiple processes access and modify shared data concurrently, and the final result depends on which process executes first.

This leads to inconsistent results and hard-to-debug errors.

---

## **How its Used**

Race conditions must be prevented in multithreaded applications, operating systems, game engines, and databases.

---

## **Example**
```c
// counter = 0
Process A: read counter (0)
Process B: read counter (0)
Process A: write 1
Process B: write 1
// Final value = 1 instead of 2
```

---

## **Details**

* Cause: lack of synchronization
* Solution: use [[Mutual Exclusion]] to protect critical sections

---

## **Related**

* [[Critical Section]]
* [[Concurrency]]
* [[Process Synchronization]]

---

## **One Line Recall**

Race Condition = result depends on execution timing.