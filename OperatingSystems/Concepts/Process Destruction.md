## Quick Summary
Process destruction is the termination of a process by the operating system, which involves freeing all resources used by the process and removing it from the system's process structures.

---

## Core Idea
- A [[Process||process]] can terminate itself or be terminated by its parent.
- The OS frees all resources associated with the process.
- References to the process are removed from system structures.
- Depending on the OS, child processes may also be destroyed.

---

## What it is
Process destruction (or process termination) is the procedure by which the operating system removes a process from the system.

A process can be destroyed in several situations:

- The process completes its execution
- The process encounters a fatal error
- The parent process explicitly terminates it
- The operating system terminates it

The destroy operation must carefully remove the process from all system data structures.

Typical steps include:

1. Recursively destroy all child processes
2. Remove the process from the ready list or resource waiting lists
3. Remove the process from its parent's child list
4. Release memory and system resources
5. Close open files
6. Deallocate the PCB
7. Call the scheduler to select the next process

---

## How its Used
Process destruction occurs frequently in operating systems.

### Program completion
When a program finishes executing, the OS destroys the process.

### Error handling
If a process crashes or causes a fatal exception, the OS terminates it.

### Parent-controlled termination
Some programs create worker processes and destroy them when tasks finish.

### System cleanup
When users log out or systems shut down, many processes are destroyed.

---

## Example

### Example 1 — Destroy Process Algorithm
```python
destroy(p):
    for all c in p.children:
        destroy(c)
    remove p from RL or waiting list
    remove p from parent.children
    release p.memory
    release p.other_resources
    close all p.open_files
    deallocate PCB

scheduler()
```

### Example 2 — Recursive Process Tree Destruction

Consider a process tree:
```
A
├── B
│   ├── D
│   └── E
└── C
```

If process **B** is destroyed:

1. Destroy D
2. Destroy E
3. Destroy B

This ensures no orphaned children remain.

---

## Details

### Resource Cleanup
When a process is destroyed, the OS must release:
- Memory allocations
- CPU scheduling entries
- Open file handles
- Hardware resources

### Recursive Destruction
Many OS implementations recursively destroy children to avoid leaving processes without parents.

### Scheduler Invocation
The scheduler is called after destruction to select the next process to run.

### Zombie Processes
In Unix-like systems, a terminated process may briefly exist as a **zombie process** until the parent reads its exit status.

---

## Related
- [[Process]]
- [[Process Creation]]
- [[PCB]]
- [[Process Scheduler]]
- [[Init Process]]

---

## One Line Recall
Process destruction removes a process from the system by freeing its resources, removing its PCB, and updating scheduling structures.