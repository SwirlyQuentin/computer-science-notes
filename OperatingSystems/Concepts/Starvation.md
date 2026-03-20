## **Quick Summary**

Starvation is when a process is indefinitely delayed because other processes keep getting access first.

---

## **Core Idea**

* Unfair scheduling prevents a process from ever progressing.

---

## **What it is**

**Starvation** occurs when a process is continually denied access to resources because other processes repeatedly take priority.

Unlike deadlock:

* The system is still running
* But some processes never get served

---

## **How its Used**

Starvation must be avoided in CPU scheduling, resource allocation systems, and concurrent algorithms.

Prevention methods include:

* Fair scheduling
* Priority aging

---

## **Example**
```
High-priority processes keep executing
Low-priority process never gets CPU time
→ The low-priority process starves
```

---

## **Details**

### In Lecture

* The `will_wait` variable ensures fairness
* Prevents one process from repeatedly entering the CS

### Difference from Deadlock

* Deadlock → system stuck
* Starvation → system works, but unfairly

---

## **Related**

* [[Deadlock]]
* [[Lockout]]
* [[Process Scheduling]]

---

## **One Line Recall**

Starvation = a process never gets its turn.