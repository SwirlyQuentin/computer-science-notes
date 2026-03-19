## **Quick Summary**

Long-term scheduling determines **which processes are allowed to enter the ready state and begin competing for CPU time**.

---

## **Core Idea**

The long-term scheduler controls **how many processes are active in the system** by deciding when processes move from the **new or suspended states** into the [[Ready List]].

---

## **What it is**

Long-term scheduling is the OS mechanism that determines **when processes should be admitted into the ready state**.

Processes are created at unpredictable times and initially enter the system in the **new state**. The long-term scheduler evaluates these processes and decides **which ones should be moved to the [[Ready List]]**, where they can compete for CPU time.

Long-term scheduling also applies when processes that were [[Process Suspended State|suspended]] are **reactivated** and allowed to return to the ready state.

Compared to [[short-term scheduling]], long-term scheduling occurs **much less frequently** and operates at a **higher time granularity**.

---

## **How its Used**

Long-term scheduling is used to:

* Control the **degree of multiprogramming** (how many processes run simultaneously)
* Prevent the system from being **overloaded with too many active processes**
* Balance system workloads between **CPU-bound and I/O-bound processes**

In modern systems, long-term scheduling decisions may occur:

* When a process is **created**
* When suspended processes are **reactivated**
* When system load must be **balanced**

---

## **Example**

### Example 1: Process Admission

Assume five processes are created:

| Process | State |
| ------- | ----- |
| P1      | New   |
| P2      | New   |
| P3      | New   |
| P4      | New   |
| P5      | New   |

The OS determines the system can efficiently run **3 processes simultaneously**.

The long-term scheduler may admit:
```
P1 → Ready List
P2 → Ready List
P3 → Ready List
```

While:
```
P4, P5 remain in the new state
```

Only the admitted processes compete for CPU time.

### Example 2: Suspended Process

A suspended process may later be **reactivated**:
```
Suspended → Long-term scheduler → Ready List
```

---

## **Details**

### Differences from [[Short-Term Scheduling]]

| Long-Term Scheduling         | [[Short-Term Scheduling]]            |
| ---------------------------- | -------------------------------- |
| Occurs infrequently          | Occurs very frequently           |
| Controls process admission   | Chooses which ready process runs |
| Operates at large time scales | Operates at millisecond scales  |

### Arrival and Departure Meaning

For long-term scheduling:

* **Arrival:** process creation
* **Departure:** process destruction

---

## **Related**

* [[Short-Term Scheduling]]
* [[Ready List]]
* [[CPU Scheduling]]
* [[Process Creation]]
* [[Process Suspended State]]

---

## **One Line Recall**

Long-term scheduling **decides which processes enter the system and compete for CPU time**.