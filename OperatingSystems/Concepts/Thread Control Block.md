---
aliases:
  - TCB
---
## **Quick Summary**

A Thread Control Block (TCB) stores the runtime information needed for a thread to execute independently.

---

## **Core Idea**

* Each thread needs its own execution state, which is stored in a TCB.

---

## **What it is**

A **Thread Control Block (TCB)** is a data structure used by the operating system or runtime system to store information about a thread.

It contains the **dynamic execution state** required for a thread to run independently.

Typical information stored in a TCB includes:

* CPU state
* Program counter
* Stack pointer
* Thread state

The TCB allows the system to pause, resume, and switch between threads.

Only minimal information is replicated in each TCB. Threads still share process-level resources stored in the **PCB**.

---

## **How its Used**

TCBs are used for:

* Thread scheduling
* Context switching
* Managing thread states

During a **context switch**:

1. The CPU state is saved to the current thread's TCB.
2. Another thread's state is loaded from its TCB.

---

## **Example**

### Thread State Example

Thread A TCB:
```
PC = 100
SP = 0x8F20
State = Running
```

Thread B TCB:
```
PC = 540
SP = 0xAA12
State = Ready
```

The scheduler can switch between them.

---

## **Details**

### Stored Information

TCBs typically store:

* Program counter
* Stack pointer
* CPU registers
* Thread state

### Relationship to PCB

Process-level information remains in the **Process Control Block**.

---

## **Related**

* [[Thread]]
* [[Process Control Block]]
* [[Program Counter]]
* [[Execution Stack]]

---

## **One Line Recall**

A TCB stores the execution state required for a thread to run independently.