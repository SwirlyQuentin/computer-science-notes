---
aliases:
  - MLF
  - Multilevel Feedback
---
## **Quick Summary**

Multilevel Feedback (MLF) Scheduling dynamically adjusts process priority based on behavior, favoring short tasks and preventing starvation.

---

## **Core Idea**

* Multiple priority queues
* Processes move between queues based on CPU usage
* Short jobs stay high priority, long jobs move lower
* [[Time quantum]] increases at lower priorities

---

## **What it is**

MLF Scheduling is an advanced CPU scheduling algorithm that improves on Multilevel (ML) scheduling by allowing processes to **change priority dynamically**.

* New processes start at the **highest priority queue**
* Each queue has its own **[[time quantum]]**
* If a process uses too much CPU time:
  * It is moved to a **lower priority queue**
* Lower queues have **longer time quantums**

General rule — at level L, max execution time:
```
2^(N-L) * Q
```

This system balances **responsiveness (short jobs)** and **fairness (long jobs still run)**.

---

## **How its Used**

* Used in **modern operating systems** (variations of it)
* Ideal for:
  * Interactive systems (terminals, GUIs)
  * Mixed workloads (short + long processes)
* Prevents **starvation** while maintaining responsiveness

---

## **Example**

Assume 3 queues (Q0, Q1, Q2) with base quantum = 10ms.

Long process P1:

1. Starts in Q0 → runs for 10ms → not finished → moves to Q1
2. Runs in Q1 → gets 20ms → not finished → moves to Q2
3. Runs in Q2 → gets 40ms

Short process P2:

* Finishes in Q0 within 10ms → never moves down

---

## **Details**

* **Aging** may be used to move long-waiting processes back up
* Prevents starvation better than ML scheduling
* Tradeoff: more complex to implement
* Key tuning parameters:
  * Number of queues
  * [[Time quantum]] scaling
  * Promotion/demotion rules

---

## **Related**

* [[Multilevel Scheduling]]
* [[RR Scheduling]]
* [[Starvation]]
* [[Process Priority]]
* [[Time Quantum]]

---

## **One Line Recall**

MLF dynamically adjusts priorities so short jobs finish fast and long jobs don't starve.