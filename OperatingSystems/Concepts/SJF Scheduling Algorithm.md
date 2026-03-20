---
aliases:
  - SJN
  - SJF
  - Shortest Job First
  - Shortest Job First (SJF)
---

## **Quick Summary**

Runs the shortest job first to minimize waiting time.

---

## **Core Idea**

* Shorter total CPU time ⇒ higher [[Process Priority|priority]]
* Optimizes average waiting and [[turnaround time]]

---

## **What it is**

SJF (Shortest Job First), also called SJN (Shortest Job Next), is a **[[Non-Preemptive Scheduling]] algorithm** that selects the process with the **smallest total CPU time requirement**.

Once selected, the process runs to completion.

---

## **How its Used**

* Used when **CPU time can be estimated**
* Common in:
  * Batch systems
  * Environments where job lengths are predictable

---

## **Example**

| Process | CPU Time |
| ------- | -------- |
| P1      | 6        |
| P2      | 2        |
| P3      | 4        |

Execution order: P2 → P3 → P1

This reduces total waiting time compared to [[FIFO Scheduling Algorithm|FIFO]].

---

## **Details**

* Requires estimation of CPU time
* Uses [[Arbitration Rule]] if times are equal
* Can cause [[Starvation]] for long jobs
* Minimizes **average [[Turnaround Time]]**

---

## **Related**

* [[SRT Scheduling Algorithm]]
* [[CPU Burst]]
* [[Starvation]]
* [[Turnaround Time]]

---

## **One Line Recall**

SJF runs the shortest job first to minimize waiting time.