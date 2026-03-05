
**Definition:**
A **context switch** is the process of saving the execution state of one process and restoring the execution state of another so the CPU can switch between them.

---

### Core Idea

A CPU can execute only **one process at a time**.

However, modern systems run many processes seemingly at once.

This illusion of parallel execution is achieved by rapidly switching the CPU between processes.

A context switch is what makes that switching possible.

It allows:
- A running process to pause
- Another process to run
- The original process to later resume exactly where it left off

---

### What Is Being Switched?

The "context" refers to the complete [[CPU State]] of a process.

This includes:

- The [[Program Counter]]
- All [[CPU Register]] values
- Hardware status flags
- Stack pointer

All of this information is stored inside the process’s [[PCB]].

---

### When Does a Context Switch Occur?

A context switch can happen when:

- A timer interrupt fires (time slice expires)
- A process enters the [[Process Blocked State||Blocked State]] (e.g., waiting for I/O)
- A higher-priority process becomes ready
- The process voluntarily yields the CPU

The decision is made by the [[Process Scheduler]].

---

### Step-by-Step Process

1. The currently running process is interrupted.
2. The OS saves its [[CPU State]] into its [[PCB]].
3. The scheduler selects another process from the ready queue.
4. The OS loads that process’s CPU State from its PCB.
5. Execution resumes from its stored [[Program Counter]].

From the process’s perspective, it appears as though it was never stopped.

---

### Why It Works

Because all execution information is preserved inside the PCB, the OS can:

- Pause a process
- Run something else
- Restore the exact execution state later

This guarantees correctness and continuity of execution.

---

### Cost of a Context Switch

A context switch does **not** perform useful program work.

It introduces overhead because:

- CPU registers must be saved and restored
- Scheduling logic must run
- Caches may be disrupted

Frequent context switching can reduce performance.

---

### Importance

Context switching enables:

- Multitasking
- Time sharing
- Responsive operating systems
- Fair CPU distribution
- Concurrent application execution

Without context switching, only one program could run at a time.

---

### Related Concepts

- [[Process]]
- [[PCB]]
- [[CPU State]]
- [[Program Counter]]
- [[CPU Register]]
- [[Process Scheduler]]
- [[Process Ready State||Ready State]]
- [[Process Blocked State||Blocked State]]