## **Quick Summary**

An arbitration rule determines **which process runs when multiple processes have the same priority**.

---

## **Core Idea**

When priorities tie, the arbitration rule **breaks the tie**.

---

## **What it is**

An arbitration rule is a decision policy used when two or more processes have **equal priority values**.

Since the scheduler cannot differentiate them by priority, it must apply a **secondary rule** to determine which process should run first.

Common arbitration strategies include:

* [[FIFO Scheduling Algorithm|First-Come First-Served]]
* [[RR Scheduling|Round Robin]]
* Random selection

---

## **How its Used**

Arbitration rules are used within scheduling algorithms to ensure that processes with equal priority are **handled fairly and predictably**.

They prevent the scheduler from making **arbitrary decisions**.

---

## **Example**

### Example: Tie in Priority

| Process | Priority |
| ------- | -------- |
| P1      | 2        |
| P2      | 2        |
| P3      | 3        |

If arbitration uses **[[FIFO Scheduling Algorithm|FCFS]]**:
```
P1 → P2 → P3
```

If arbitration uses **[[RR Scheduling|Round Robin]]**:
```
P1 → P2 → P1 → P2 ...
```

---

## **Details**

Without arbitration rules, scheduling would be **undefined when priorities match**.

---

## **Related**

* [[Process Priority]]
* [[Short-Term Scheduling]]
* [[CPU Scheduling]]

---

## **One Line Recall**

Arbitration rules **resolve ties between processes with equal priority**.