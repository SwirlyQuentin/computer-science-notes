## **Quick Summary**

Preemptive scheduling allows the OS to **interrupt a running process and give the CPU to another process**.

---

## **Core Idea**

The scheduler can **force a context switch** even if the running process has not finished.

---

## **What it is**

In preemptive scheduling, the operating system can **stop the currently running process and assign the CPU to another process**.

This occurs when certain events happen, such as:

* A **new process enters the [[Ready List|RL]]**
* A **blocked process becomes ready again**
* A **timer interrupt occurs**

Preemption ensures that **no single process monopolizes the CPU**.

---

## **How its Used**

Preemptive scheduling is commonly used in:

* **modern multitasking operating systems**
* **time-sharing systems**
* **real-time systems**

Benefits include:

* improved responsiveness
* fair CPU distribution
* better support for interactive applications

Examples of preemptive algorithms:

* Round Robin
* [[Process Priority|Priority]] Scheduling with preemption
* Multilevel Feedback Queue

---

## **Example**

### Example 1: Timer Interrupt
```
Running: P1
Time quantum = 10ms
```

After 10ms:
```
Timer interrupt occurs
```

Scheduler chooses:
```
P2 → CPU
```

### Example 2: Higher Priority Arrival
```
Running: P1 (priority 3)
```

New process arrives:
```
P2 (priority 1)
```

Scheduler preempts:
```
P1 → Ready List
P2 → CPU
```

---

## **Details**

### Context Switching

Preemption requires **context switching**, which involves:

* saving CPU registers
* saving program counter
* restoring another process state

Context switching introduces **overhead**, but improves fairness.

---

## **Related**

* [[Non-Preemptive Scheduling]]
* [[Short-Term Scheduling]]
* [[Process Priority]]
* [[Context Switch]]

---

## **One Line Recall**

Preemptive scheduling allows the OS to **interrupt a running process to run another process**.