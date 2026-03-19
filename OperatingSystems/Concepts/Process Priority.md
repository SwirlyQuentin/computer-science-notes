---
aliases:
  - Priority
---

## **Quick Summary**

Process priority is a **numerical value representing the importance of a process relative to others**.

---

## **Core Idea**

The scheduler uses priority values to **decide which process should run next**.

---

## **What it is**

Process priority is a value assigned to each process (or thread) that determines **its scheduling preference**.

Processes with **higher priority** are typically scheduled before lower priority ones.

Priorities may be:

* **Static** – assigned at creation
* **Dynamic** – change during execution

Priority decisions may be influenced by:

* arrival time
* attained CPU time
* deadlines
* external priority values
* system load

---

## **How its Used**

Priorities are used to:

* determine scheduling order
* support real-time requirements
* ensure important processes run sooner

Many scheduling algorithms rely on priority values.

---

## **Example**

### Example: Priority Scheduling

| Process | Priority |
| ------- | -------- |
| P1      | 3        |
| P2      | 1        |
| P3      | 2        |

Execution order:
```
P2 → P3 → P1
```

Lower number = higher priority.

---

## **Details**

### Dynamic Priority Adjustments

Operating systems may adjust priorities to:

* prevent **starvation**
* favor **interactive tasks**
* penalize CPU-heavy tasks

---

## **Related**

* [[Arbitration Rule]]
* [[Short-Term Scheduling]]
* [[CPU Burst]]
* [[Deadline (Scheduling)]]

---

## **One Line Recall**

Process priority determines **which processes get CPU time first**.---