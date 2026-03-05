
**Definition:**
A **CPU register** is a small, extremely fast storage location inside the processor used to hold data and instructions that are actively being used during execution.

---

### Core Idea

The CPU needs immediate access to certain values while executing instructions.

Instead of reading and writing to main memory (which is slower), it uses registers.

Registers are:
- Located directly inside the CPU
- Very limited in number
- Extremely fast compared to RAM

They store the temporary data that allows instructions to execute efficiently.

---

### What Registers Store

Registers can hold:

- Intermediate arithmetic results
- Memory addresses
- Function parameters
- Return values
- Loop counters
- Stack location
- The [[Program Counter]]
- Status flags

If a process is running, its working data lives in registers.

---

### Types of CPU Registers

#### 1. General-Purpose Registers
Used for:
- Arithmetic
- Logic operations
- Temporary data storage

Example uses:
- `R1 = R2 + R3`
- Storing loop counters

---

#### 2. Special-Purpose Registers

These have specific roles:

- **[[Program Counter]]** → address of next instruction
- **Stack Pointer (SP)** → top of the execution stack
- **Frame/Base Pointer (FP/BP)** → tracks function stack frames
- **Status/Flag Register** → holds condition flags (zero, carry, overflow)

---

### Registers and the CPU State

All register values together form part of the [[CPU State]].

During a [[Context Switch]]:

1. The OS saves all register values into the process’s [[PCB]].
2. Another process’s register values are restored.
3. Execution continues from the restored state.

If even one register is restored incorrectly, execution may fail.

---

### Why Registers Matter

Registers are critical because:

- Every instruction operates on them.
- They determine current computation progress.
- They hold execution control information.
- They must be preserved for multitasking.

Without registers:
- The CPU could not execute instructions efficiently.
- Context switching would not be possible.
- Processes could not resume correctly.

---

### Registers vs Main Memory

**Registers**
- Inside CPU
- Extremely fast
- Very limited quantity
- Used for active computation

**Main Memory (RAM)**
- Outside CPU
- Slower than registers
- Large capacity
- Used for program storage and data

Registers act as the CPU’s working area.

---

### Importance

CPU registers enable:

- Fast instruction execution
- Efficient computation
- Accurate process resumption
- Reliable multitasking

They are fundamental to how processors work.

---

### Related Concepts

- [[CPU State]]
- [[Program Counter]]
- [[Context Switch]]
- [[PCB]]
- [[Stack]]
- [[Process]]