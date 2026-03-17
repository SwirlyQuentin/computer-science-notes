## (Process Control Block)

**Definition:**
A **[[Process]] Control Block (PCB)** is a data structure used by the [[Operating System]] to store all information needed to manage and track a [[process]].

---

### Core Idea

The operating system cannot directly "see" a process.

Instead, it keeps a record of each process in a structured data object — the PCB.

You can think of the PCB as:

> The OS’s official record for a process.

Every process has exactly one PCB.
If a process exists, its PCB exists.

When the OS needs to pause, resume, schedule, or terminate a process, it interacts with the PCB.

---

### What the PCB Contains

The PCB stores everything required to fully describe a process, including:

#### 1. Process State
- [[Process Ready State||Ready State]]
- [[Process Running State||Running State]]
- [[Process Blocked State||Blocked State]]
- [[Process Suspended State||Suspended State]]
- [[Process Terminated State||Terminated State]]

This tells the OS what the process is currently doing.

---

#### 2. CPU Information
- [[Program Counter]] (next instruction to execute)
- All [[CPU Register]] values
- Hardware status flags

Together, these make up the [[CPU State]].

This information is saved during a [[Context Switch]].

---

#### 3. Memory Information
- Pointers to code segment
- Stack location
- Heap information
- Memory boundaries

This ensures processes do not interfere with each other’s memory.

---

#### 4. Scheduling Information
- Priority
- Time slice information
- Queue position

Used by the [[Process Scheduler]] to decide which process runs next.

---

#### 5. Resource Information
- Open files
- I/O devices
- Locks
- Other allocated system resources

---

### Role in Context Switching

During a [[Context Switch]]:

1. The OS saves the current process’s [[CPU State]] into its PCB.
2. The OS selects another process.
3. The OS loads that process’s CPU State from its PCB.
4. Execution resumes.

Without the PCB, resuming a paused process exactly where it left off would be impossible.

---

### Lifecycle of a PCB

- Created when a process is created.
- Updated as the process runs.
- Used throughout scheduling and execution.
- Deleted when the process fully terminates.

The PCB exists for the entire lifetime of the process.

---

### Importance

The PCB is essential for:

- Multitasking
- Safe process isolation
- Accurate context switching
- CPU scheduling
- Resource management

It is the core data structure that makes process management possible.

---

### Related Concepts

- [[Process]]
- [[Program Counter]]
- [[CPU State]]
- [[CPU Register]]
- [[Context Switch]]
- [[Process Scheduler]]
- [[Process Ready State||Ready State]]
- [[Process Running State||Running State]]
- [[Process Blocked State||Blocked State]]