---
aliases:
  - Deadline
---
## **Quick Summary**

A deadline is the **time by which a process must finish its execution**.

---

## **Core Idea**

Deadlines are used in scheduling systems where **timing constraints are critical**.

---

## **What it is**

A deadline is a specific point in time by which a process must complete its work.

Deadlines are especially important in **real-time systems**, where missing a deadline can lead to system failure.

Processes may also have a **period**, meaning their tasks repeat at regular intervals and each period ends with a deadline.

---

## **How its Used**

Deadlines are used in:

* real-time operating systems
* embedded systems
* scheduling algorithms like **Earliest Deadline First (EDF)**

They ensure time-sensitive tasks complete on time.

---

## **Example**

### Example 1: Real-Time Task

Task must finish within **20ms**:
```
Start:    0ms
Deadline: 20ms
```

If execution takes **15ms** → success
If execution takes **25ms** → deadline missed

### Example 2: Periodic Task

Sensor reading every **100ms**:
```
Period:   100ms
Deadline: end of each period
```

---

## **Details**

### Types of Deadlines

**Hard Deadline**
* Must never be missed

**Soft Deadline**
* Missing occasionally is acceptable but undesirable

---

## **Related**

* [[Process Priority]]
* [[Short-Term Scheduling]]
* [[Period (Real-Time Scheduling)]]

---

## **One Line Recall**

A deadline is the **time by which a process must finish its work**.