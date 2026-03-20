## **Quick Summary**

Response Time is how long it takes from a user request to the start of the system's response.

---

## **Core Idea**

* Measures system responsiveness
* Critical for interactive systems
* Affected by scheduling decisions

---

## **What it is**

Response Time is the **elapsed time between a request and the first visible response**.

* Starts: when user submits input (click, keypress)
* Ends: when output begins appearing

It does **not** measure total completion time — just the initial reaction.

---

## **How its Used**

* Key metric in:
  * Interactive systems
  * User experience evaluation
* Used to:
  * Compare scheduling algorithms
  * Tune time quantum values

---

## **Example**

Typing a character:
```
Press key → character appears in 50ms → response time = 50ms
```

Running a command:
```
Click button → loading starts after 200ms → response time = 200ms
```

Multi-process system:
```
More processes → longer wait before CPU is allocated
```

---

## **Details**

Response time increases with:

* Number of processes
* Length of time quantum
* Context switch overhead

Important distinction:

* **Response Time ≠ [[Turnaround Time]]**

Goal: keep response time **low enough to feel instant**.

---

## **Related**

* [[Turnaround Time]]
* [[Time Quantum]]
* [[Context Switch]]
* [[Interactive Process]]

---

## **One Line Recall**

Response Time is how quickly the system starts reacting to a user request.