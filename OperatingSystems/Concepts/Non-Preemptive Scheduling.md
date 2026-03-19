## **Quick Summary**

Non-preemptive scheduling allows a process to **keep the CPU until it finishes or blocks**.

---

## **Core Idea**

The OS **does not forcibly interrupt** a running process.

---

## **What it is**

In non-preemptive scheduling, once a process begins executing on the CPU, it continues until:

* the process **terminates**, or
* the process **blocks on a resource**

The scheduler does not intervene during execution.

This type of scheduling is simpler and has **lower overhead** because it avoids frequent context switches.

---

## **How its Used**

Non-preemptive scheduling is used in:

* early operating systems
* simple embedded systems
* environments where context switching overhead must be minimized

Common non-preemptive algorithms:

* First-Come First-Served (FCFS)
* Non-preemptive [[Process Priority|priority]] scheduling

---

## **Example**

### Example 1: FCFS Scheduling

Ready List:
```
P1
P2
P3
```

Execution order:
```
P1 runs completely
P2 runs completely
P3 runs completely
```

Even if P2 is very short, it must wait.

### Example 2: Blocking Event
```
Running: P1
```

P1 requests disk I/O:
```
P1 → Blocked
```

Scheduler selects:
```
P2 → CPU
```

---

## **Details**

### Advantages

* Simple implementation
* Lower scheduling overhead

### Disadvantages

* Poor responsiveness
* Can cause **convoy effect**

---

## **Related**

* [[Preemptive Scheduling]]
* [[Short-Term Scheduling]]
* [[CPU Scheduling]]

---

## **One Line Recall**

Non-preemptive scheduling lets a process **run until it finishes or blocks**.