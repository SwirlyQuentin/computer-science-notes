---
aliases:
  - Scheduler
---

**Definition:**
The **Process Scheduler** is the component of the operating system responsible for selecting which ready [[process]] gets to run on the CPU next.

---

### Core Idea

At any given moment:

- Many processes may be in the [[Process Ready State||Ready State]].
- Only one process can be in the [[Process Running State||Running State]] per CPU core.

The scheduler decides:

> Which process gets the CPU, and for how long.

It enables multitasking by coordinating CPU time among processes.

---

### Why the Scheduler Is Needed

Since multiple processes compete for the CPU, the OS must:

- Distribute CPU time fairly
- Maintain system responsiveness
- Enforce [[Process Priority|priority]] rules
- Prevent [[starvation]]
- Optimize performance

Without a scheduler, only one process could run.

---

### What the Scheduler Works With

The scheduler relies on:

- The **ready queue** (list of processes ready to run)
- Each process’s [[PCB]]
- Scheduling information (priority, time slice, etc.)
- Timer interrupts

When a scheduling decision is made, the OS performs a [[Context Switch]].

---

### How Scheduling Happens

Typical flow:

1. A process enters the [[Process Ready State||Ready State]].
2. The scheduler selects a process from the ready queue.
3. The OS performs a [[Context Switch]].
4. The selected process enters the [[Process Running State||Running State]].
5. When its time expires or it blocks, the scheduler runs again.

This cycle repeats continuously.

---

### Scheduling Policies

The scheduler uses a [[Scheduling Algorithm]] to make decisions.

Examples include:

- First-Come, First-Served ([[FIFO Scheduling Algorithm|FCFS]])
- [[RR Scheduling|Round Robin]]
- [[Process Priority|Priority]] Scheduling
- [[SJF Scheduling Algorithm|Shortest Job First (SJF)]]

Different algorithms optimize for different goals:
- Fairness
- Throughput
- [[Response time]]
- CPU utilization

---

### Preemptive vs Non-Preemptive Scheduling

**[[Preemptive Scheduling]]**
- The OS can interrupt a running process.
- More responsive.
- Used in modern operating systems.

**[[Non-Preemptive Scheduling]]**
- A process keeps the CPU until it blocks or finishes.
- Simpler but less responsive.

Most modern systems use [[preemptive scheduling]].

---

### Relationship to Context Switching

The scheduler:
- Decides *which* process runs.

The [[Context Switch]]:
- Performs the technical work of switching execution.

They work together to enable multitasking.

---

### Importance

The Process Scheduler enables:

- Multitasking
- Fair CPU allocation
- Responsive user interfaces
- Efficient resource utilization
- [[Process Priority|Priority]]-based execution

It is the decision-making engine of process management.

---

### Related Concepts

- [[Process]]
- [[PCB]]
- [[Context Switch]]
- [[Process Ready State||Ready State]]
- [[Process Running State||Running State]]
- [[Process Blocked State||Blocked State]]
- [[Scheduling Algorithm]]
- [[Time Sharing]]