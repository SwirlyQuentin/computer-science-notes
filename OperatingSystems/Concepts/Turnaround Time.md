---
aliases:
  - Turnaround
---
## **Quick Summary**

Total time from when a process arrives to when it finishes.

---

## **Core Idea**

* Measures overall process performance
* Includes both execution and waiting time

---

## **What it is**

The **turnaround time** of a [[Process]] is the time from arrival to completion.

It includes:

* CPU execution time
* Waiting time in the ready queue

---

## **How its Used**

* Used to evaluate scheduling algorithms
* Key metric in:
  * Batch systems
  * Performance comparisons

---

## **Example**

Process:

* Arrival = 0
* CPU Time = 5
* Waiting Time = 3

Turnaround Time:
```
= 5 + 3 = 8
```

Average Turnaround Time (ATT) across all processes:
```
ATT = sum of all turnaround times / n
```

---

## **Details**

* Scheduling cannot reduce CPU time, only waiting time
* Lower turnaround time = better performance
* Influenced heavily by scheduling algorithm

---

## **Related**

* [[Waiting Time]]
* [[FIFO Scheduling Algorithm]]
* [[SJF Scheduling Algorithm]]
* [[SRT Scheduling Algorithm]]

---

## **One Line Recall**

Turnaround time = total time from arrival to completion.