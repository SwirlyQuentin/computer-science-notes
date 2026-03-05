
**Definition:**
A **process** is an instance of a program that is actively being executed by an operating system.

---

### Core Idea

A program by itself is just static instructions stored on disk.

A process is what you get when:
1. The operating system loads a program into memory.
2. Allocates resources for it.
3. Begins executing its instructions.

A process is therefore a **living, running program** with its own execution state and resources.

Each running instance of a program is a separate process.

If you open the same application twice:
- You get two processes.
- Each has its own memory.
- Each has its own execution state.
- Each is tracked independently by the OS.

---

### What Makes Up a Process

A process includes:

- Program code (text segment)
- Data (variables, heap memory)
- [[Execution Stack]]
- Allocated system resources (files, I/O, etc.)
- A [[Program Counter]]
- A complete [[CPU State]]
- A [[PCB]] (Process Control Block)

The [[PCB]] is how the OS keeps track of everything about the process.

---

### Process vs Program

**Program**
- Passive
- Stored on disk
- Just instructions

**Process**
- Active
- Running instance of a program
- Has memory, state, and resources

A program becomes a process when the OS begins executing it.

---

### Process States

During its lifetime, a process moves between states:

- [[Process Ready State||Ready State]] -> waiting for CPU time
- [[Process Running State||Running State]] -> currently executing
- [[Process Blocked State||Blocked State]] -> waiting for a resource or event
- [[Process Suspended State||Suspended State]] -> paused by the OS
- [[Process Terminated State||Terminated State]] -> finished execution

These transitions are controlled by the operating system.

---

### Importance

Processes are the foundation of modern operating systems.

They enable:

- Multitasking
- Program isolation
- Controlled resource allocation
- [[Time Sharing||CPU sharing]] (time sharing)
- Safe execution of multiple applications

Without processes, the OS could not manage multiple running programs safely or efficiently.

---

### Related Concepts

- [[PCB]]
- [[Program Counter]]
- [[CPU State]]
- [[Context Switch]]
- [[Process Scheduler]]
- [[Threads]]