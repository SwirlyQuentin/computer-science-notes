
**Definition:**
A **scheduling algorithm** is the policy used by the operating system to decide which [[process]] in the ready queue should run next on the CPU.

---

### Core Idea

Multiple processes may be in the [[Process Ready State||Ready State]] at the same time.

The [[Process Scheduler]] must choose one of them.

The scheduling algorithm defines the rule used to make that choice.

It determines:

- Who runs next
- How long they run
- In what order processes are served

Different algorithms prioritize different goals.

---

### What Scheduling Algorithms Try to Optimize

Common system goals include:

- **Fairness** -> Every process gets CPU time
- **Throughput** -> Maximize number of completed processes
- **Response Time** -> Fast reaction for interactive tasks
- **Turnaround Time** -> Minimize total time from start to finish
- **CPU Utilization** -> Keep CPU busy as much as possible
- **Avoid Starvation** -> Prevent processes from waiting forever

No single algorithm optimizes all goals perfectly.

---

### Common Scheduling Algorithms

#### 1. First-Come, First-Served (FCFS)

- Processes run in the order they arrive.
- Non-preemptive.
- Simple but can cause long wait times.
- Suffers from the "convoy effect."

---

#### 2. Shortest Job First (SJF)

- Process with shortest expected runtime runs first.
- Minimizes average turnaround time.
- Hard to implement because runtime must be estimated.
- Can cause starvation of long jobs.

---

#### 3. Priority Scheduling

- Each process has a priority value.
- Higher-priority processes run first.
- Can be preemptive or non-preemptive.
- May cause starvation without priority aging.

---

#### 4. Round Robin (RR)

- Each process gets a fixed time slice (quantum).
- Preemptive.
- Fair and widely used.
- Smaller time slice → more context switches.
- Larger time slice → behaves more like FCFS.

---

### Preemptive vs Non-Preemptive

**Preemptive**
- The OS can interrupt a running process.
- Improves responsiveness.
- Used in modern operating systems.

**Non-Preemptive**
- A process runs until it blocks or finishes.
- Simpler but less responsive.

---

### Relationship to the [[Process Scheduler|Scheduler]]

The scheduling algorithm is the **decision rule**.

The [[Process Scheduler]] is the component that applies that rule and triggers a [[Context Switch]] when needed.

---

### Importance

Scheduling algorithms determine:

- System responsiveness
- User experience
- Performance efficiency
- Fairness between processes

They are a core design decision in any operating system.

---

### Related Concepts

- [[Process Scheduler]]
- [[Context Switch]]