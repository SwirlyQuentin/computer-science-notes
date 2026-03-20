## **Quick Summary**

Short-term scheduling determines **which ready process gets the CPU next**.

---

## **Core Idea**

The short-term scheduler continuously selects a process from the [[Ready List]] and assigns it to the CPU.

---

## **What it is**

Short-term scheduling is the mechanism that decides **which ready process should run on the CPU at a given moment**.

Processes in the [[Ready List]] are all eligible to run, but the CPU can execute **only one process at a time per core**. The short-term scheduler evaluates all ready processes and selects one based on a scheduling algorithm.

This scheduler operates **very frequently**, often every:

* context switch
* interrupt
* process block
* process completion

Because of this frequency, short-term scheduling must be **very efficient**.

---

## **How its Used**

Short-term scheduling is used to:

* Allocate CPU time among processes
* Implement scheduling algorithms like [[FIFO Scheduling Algorithm|First-Come First-Served]], [[RR Scheduling|Round Robin]], and [[Process Priority|Priority]] Scheduling
* Ensure fair CPU usage
* Improve system responsiveness

It runs whenever:

* a process blocks
* a process finishes
* a new process enters the [[Ready List]]
* a timer interrupt occurs

---

## **Example**

### Example 1: Ready List Selection

Ready List:
```
P1
P2
P3
P4
```

If the scheduler uses **priority scheduling**:
```
P2 has the highest priority → runs next
```

### Example 2: Blocked Process
```
Running: P1
```

P1 requests disk I/O:
```
P1 → Blocked
```

Short-term scheduler selects the next process:
```
P2 → CPU
```

---

## **Details**

### Scheduler Frequency

Short-term scheduling occurs **very frequently**, sometimes **thousands of times per second**.

### CPU Core Consideration

On multi-core systems:

* each CPU core runs its **own scheduling decisions**
* the scheduler distributes processes across cores

---

## **Related**

* [[Long-Term Scheduling]]
* [[Ready List]]
* [[CPU Scheduling]]
* [[Process Priority]]
* [[Preemptive Scheduling]]

---

## **One Line Recall**

Short-term scheduling **chooses which ready process runs on the CPU next**.