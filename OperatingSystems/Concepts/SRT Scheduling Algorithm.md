---
aliases:
  - SRT
  - Shortest Remaining Time
---
## **Quick Summary**

Always runs the process with the least remaining time, interrupting others if needed.

---

## **Core Idea**

* Shorter remaining time ⇒ higher [[Process Priority|priority]]
* Dynamically re-evaluates scheduling decisions

---

## **What it is**

SRT (Shortest Remaining Time) is the **[[Preemptive Scheduling]] version of [[SJF Scheduling Algorithm]]**.

The scheduler continuously checks which process has the **smallest remaining CPU time**, and can **preempt (interrupt)** the current process if a shorter job arrives.

---

## **How its Used**

* Used in systems needing **fast response times**
* Common in:
  * Interactive systems
  * Real-time approximations

---

## **Example**

| Process | Arrival | CPU Time |
| ------- | ------- | -------- |
| P1      | 0       | 8        |
| P2      | 1       | 4        |

Execution:

* P1 starts at time 0
* At time 1, P2 arrives (shorter remaining time)
* P1 is interrupted → P2 runs first

---

## **Details**

* Requires continuous monitoring of processes
* More overhead than SJF
* Can cause [[Starvation]] for long processes
* Provides better average [[Turnaround Time]] than SJF in many cases

---

## **Related**

* [[SJF Scheduling Algorithm]]
* [[Preemptive Scheduling]]
* [[CPU Burst]]
* [[Starvation]]

---

## **One Line Recall**

SRT always runs the job with the shortest remaining time, even if it must interrupt others.