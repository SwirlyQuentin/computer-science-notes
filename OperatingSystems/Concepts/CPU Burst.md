---
aliases:
  - Burst
---

## **Quick Summary**

A CPU burst is the **amount of CPU time a process uses before it blocks or performs I/O**.

---

## **Core Idea**

Processes alternate between **CPU bursts and I/O bursts** during execution.

---

## **What it is**

A CPU burst represents the period during which a process **actively executes instructions on the CPU**.

Programs typically follow a pattern:
```
CPU burst → I/O wait → CPU burst → I/O wait
```

For short-term scheduling, the **total CPU time required by a process** may be referred to as its CPU burst.

---

## **How its Used**

CPU burst information helps scheduling algorithms:

* predict process behavior
* optimize CPU usage
* improve responsiveness

Algorithms such as **Shortest Job First (SJF)** rely heavily on CPU burst estimates.

---

## **Example**

### Example 1: CPU/IO Cycle

Process execution pattern:
```
CPU: 5ms
I/O: 20ms
CPU: 3ms
I/O: 15ms
CPU: 4ms
```

CPU bursts:
```
5ms, 3ms, 4ms
```

### Example 2: Scheduling Decision

Two processes:
```
P1: CPU burst 10ms
P2: CPU burst 3ms
```

Shortest Job First runs:
```
P2 → P1
```

---

## **Details**

### CPU-bound vs I/O-bound

* **CPU-bound processes:** long CPU bursts
* **I/O-bound processes:** short CPU bursts

---

## **Related**

* [[Short-Term Scheduling]]
* [[Process Priority]]
* [[CPU Scheduling]]

---

## **One Line Recall**

A CPU burst is the **time a process spends actively executing on the CPU**.