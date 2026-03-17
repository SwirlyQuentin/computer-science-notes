## Quick Summary
Process creation is the mechanism by which an operating system generates a new process from an existing one. A running process requests the OS to create a child process, and the OS initializes the necessary data structures and scheduling information so the new process can run.

---

## Core Idea
- A currently running [[Process||process]] requests the OS to create a new process.
- The OS allocates a new **[[PCB||Process Control Block (PCB)]]** for the process.
- The new process is inserted into system scheduling structures.
- The parent-child relationship between processes is recorded.
- The [[Process Scheduler||scheduler]] decides whether the parent or child runs next.

---

## What it is
Process creation is an operating system operation that allows a running process to spawn another process. This new process is called a **child process**, and the creating process is called the **parent process**.

When a process is created, the OS must construct all the data structures needed to manage it. The most important structure is the **[[PCB||PCB (Process Control Block)]]**, which stores:

- [[CPU State||CPU state]]
- Memory allocation information
- Scheduling data
- Accounting information
- Parent-child relationships

In most operating systems, processes are organized in a **process hierarchy**, where each process can create additional children.

The OS performs several steps during creation:

1. Allocate a new PCB
2. Initialize the CPU state and memory information
3. Set scheduling and accounting information
4. Set the process state to **[[Process Ready State||ready]]**
5. Set the parent pointer to the calling process
6. Insert the process into the parent's children list
7. Insert the process into the **ready list**
8. Call the [[Process Scheduler||scheduler]] to determine which process runs next

---

## How its Used
Process creation is used whenever a program needs to run another program or divide work into multiple concurrent tasks.

Common uses include:

### Running programs
When a user launches an application, the OS creates a new process for that program.

### Parallel computation
Programs create child processes to perform independent tasks simultaneously.

### Operating system services
The OS itself creates system processes to handle background operations.

### User sessions
When a user logs in, a process is created to manage the user's environment.

In **Unix-like systems**, process creation commonly occurs using the `fork()` system call followed by `exec()` to run a new program.

---

## Example

### Example 1 — Process Creation Algorithm
```python
create(state0, mem0, sched0, acc0):
    p = allocate new PCB
    p.cpu_state = state0
    p.memory = mem0
    p.scheduling_information = sched0
    p.accounting_information = acc0
    p.process_state = ready
    p.parent = self
    p.children = NULL
    p.open_files = NULL
    p.other_resources = NULL
    insert p into self.children
    insert p into RL
    scheduler()
    return p
```

### Example 2 — Unix Process Creation

A Unix process creating a new process:
```
pid = fork()

if pid == 0:
    exec("program")
else:
    wait(pid)
```

Here:
- `fork()` duplicates the parent process
- The child runs a new program using `exec()`

---

## Details

### Parent and Child Processes
Each created process has a parent. This relationship forms a process tree.

### Ready List (RL)
The ready list is the queue of processes ready to execute on the CPU.

### Scheduling Interaction
After creation, the scheduler decides whether the new child or the parent executes next.

### Resource Initialization
At creation time, processes typically start with:
- No children
- No open files
- No additional resources

---

## Related
- [[Process]]
- [[PCB]]
- [[Process Destruction]]
- [[Process Scheduler]]
- [[Init Process]]

## One Line Recall
Process creation is the OS operation that initializes a new process, links it to its parent, and places it in the scheduling system.