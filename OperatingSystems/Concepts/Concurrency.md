## **Quick Summary**

Concurrency is when multiple processes or threads make progress at the same time, either by running in parallel or by sharing CPU time.

---

## **Core Idea**

* Concurrency allows multiple tasks to execute in overlapping time periods, improving efficiency and responsiveness.

---

## **What it is**

**Concurrency** is the execution of multiple processes or threads in a way that they appear to run simultaneously.

This can happen in two ways:

* **Parallelism** → multiple CPUs execute processes at the same time
* **Time-sharing** → a single CPU rapidly switches between processes

Even on a single CPU, fast switching creates the illusion that processes are running at the same time.

Concurrency introduces complexity because processes may interact, especially when sharing data.

---

## **How its Used**

Concurrency is used in almost all modern systems:

* Operating systems managing multiple processes
* Game engines (AI, physics, rendering running together)
* Web servers handling many users at once
* Multithreaded applications for performance

It is critical for:

* Responsiveness (UI doesn't freeze)
* Efficiency (better CPU usage)

---

## **Example**

### Single CPU (Time-Sharing)
```
Process A runs briefly
CPU switches to Process B
CPU switches back to A
```

This happens so fast it looks simultaneous.

### Multi-Core CPU (Parallelism)
```
Process A runs on Core 1
Process B runs on Core 2
```

Both truly run at the same time.

---

## **Details**

### Concurrency vs Parallelism

* Concurrency = structure (multiple tasks in progress)
* Parallelism = actual simultaneous execution

### Challenges

Concurrency introduces problems like:

* [[Race Condition]]
* [[Deadlock]]
* [[Starvation]]

---

## **Related**

* [[Critical Section]]
* [[Process Synchronization]]
* [[Race Condition]]
* [[Deadlock]]

---

## **One Line Recall**

Concurrency = multiple processes making progress at the same time.