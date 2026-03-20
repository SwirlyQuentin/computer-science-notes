## **Quick Summary**

Time Quantum is the fixed time slice a process can use the CPU before being preempted.

---

## **Core Idea**

* Limits CPU usage per process
* Enables fair scheduling
* Controls responsiveness vs overhead

---

## **What it is**

Time Quantum (Q) is a **small unit of CPU time** assigned to processes in preemptive scheduling algorithms like [[RR Scheduling]].

* Typically ranges from **10–100 ms**
* When Q expires:
  * The process is **interrupted (preempted)**
  * Moved to the back of the queue (in RR)

---

## **How its Used**

* Core component of:
  * [[RR Scheduling]]
  * [[MLF Scheduling]]
* Determines:
  * System responsiveness
  * Efficiency of CPU usage

---

## **Example**

If Q = 20ms and a process needs 50ms total:
```
Runs in chunks: 20ms → 20ms → 10ms
```

---

## **Details**

**Small Q**
* Faster [[response time]]
* High context switching overhead

**Large Q**
* Lower overhead
* Worse responsiveness

Extreme cases:

* Q → ∞ → behaves like FCFS
* Q → very small → excessive overhead

---

## **Related**

* [[RR Scheduling]]
* [[Context Switch]]
* [[Response Time]]
* [[Preemptive Scheduling]]

---

## **One Line Recall**

Time Quantum is the max time a process can run before being forced to give up the CPU.