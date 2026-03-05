
**Definition:**
The **CPU State** is the complete snapshot of all processor information required to pause and later resume a process correctly.

---

### Core Idea

When a process is running, the CPU contains temporary information that represents the process’s current execution.

If the process is interrupted, that information must be preserved.

The CPU State is that preserved execution snapshot.

It allows a process to:

- Stop execution
- Let another process run
- Later resume as if it was never interrupted

Without saving the CPU State, execution could not continue correctly.

---

### What the CPU State Includes

The CPU State consists of:

#### 1. [[Program Counter]]
- The memory address of the next instruction to execute.
- Critical for resuming execution at the correct location.

---

#### 2. [[CPU Register]] Values
- General-purpose registers
- Stack pointer
- Base/frame pointer
- Index registers

These hold intermediate computation values.

---

#### 3. Hardware Status Flags
- Zero flag
- Carry flag
- Overflow flag
- Interrupt flag

These flags affect control flow and arithmetic behavior.

---

### Where the CPU State Is Stored

When a [[Context Switch]] occurs:

1. The OS saves the CPU State into the process’s [[PCB]].
2. Another process’s CPU State is loaded from its PCB.
3. The CPU resumes execution using that restored state.

The CPU State lives:
- In hardware while running
- In the PCB while paused

---

### Why It Matters

The CPU State guarantees:

- Correct continuation of execution
- Reliable multitasking
- Safe process switching
- Accurate computation results

If even one register were restored incorrectly, the process could:

- Crash
- Corrupt data
- Produce incorrect results

---

### CPU State vs Process State

**CPU State**
- Low-level hardware execution snapshot
- Registers + Program Counter + flags

**Process State**
- High-level scheduling status
- Ready, Running, Blocked, etc.

The CPU State determines *how* execution resumes.
The Process State determines *when* execution resumes.

---

### Importance

The CPU State is essential for:

- [[Context Switch]]
- Multitasking
- Preemptive scheduling
- Process isolation
- Reliable OS behavior

It is the mechanism that makes pausing and resuming processes possible.

---

### Related Concepts

- [[Process]]
- [[PCB]]
- [[Context Switch]]
- [[Program Counter]]
- [[CPU Register]]