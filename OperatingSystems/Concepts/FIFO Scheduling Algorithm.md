---
aliases:
  - FCFS
  - FIFO
  - First-Come First-Served
---

## **Quick Summary**

Runs processes in the exact order they arrive—first come, first served.

---

## **Core Idea**

* Processes are scheduled strictly by [[Process]] arrival time
* Earlier arrival ⇒ higher [[Process Priority|priority]]
* No interruption once a process starts

---

## **What it is**

FIFO (First-In-First-Out), also called FCFS (First-Come-First-Serve), is a **[[Non-Preemptive Scheduling]] algorithm** where processes are executed in the order they enter the ready queue.

Once a process begins execution, it runs until completion before the next process starts.

---

## **How its Used**

* Used in simple systems and early operating systems
* Common in **batch processing systems**
* Useful when:
  * Processes are similar in size
  * Simplicity is preferred over performance

---

## **Example**

Processes arrive in this order:

| Process | Arrival | CPU Time |
| ------- | ------- | -------- |
| P1      | 0       | 5        |
| P2      | 1       | 3        |
| P3      | 2       | 2        |

Execution order: P1 → P2 → P3

Waiting times:

* P1 = 0
* P2 = 5
* P3 = 8

---

## **Details**

* Suffers from **convoy effect** (long jobs delay short ones)
* Uses [[Arbitration Rule]] if arrival times are identical
* Very simple but inefficient for mixed workloads

---

## **Related**

* [[Process]]
* [[Non-Preemptive Scheduling]]
* [[Turnaround Time]]
* [[Waiting Time]]

---

## **One Line Recall**

FIFO runs processes in arrival order with no interruption.