## **Quick Summary**

An interactive process is a program that continuously communicates with the user, requiring fast responses to inputs like typing or clicking.

---

## **Core Idea**

* Involves direct user interaction
* Alternates between input → processing → output
* Requires fast response time
* Relies on CPU time-sharing

---

## **What it is**

An interactive process is a type of process that:

* Receives commands or data from a user (keyboard, mouse, etc.)
* Produces immediate output on a display or terminal

It operates in a dialog-like manner, meaning:

* The user provides input
* The system responds
* The cycle repeats

Because of this continuous interaction, the process must:

* Be scheduled frequently
* Not be blocked for long periods

To achieve this, operating systems use [[Preemptive Scheduling]] so multiple interactive processes can share the CPU efficiently.

---

## **How its Used**

* Common in:
  * Command-line interfaces (CLI)
  * Graphical user interfaces (GUI)
  * Text editors, browsers, games
* Critical for:
  * User experience
  * Real-time feedback systems

Poor handling → lag, freezing, bad UX. Good scheduling → smooth, responsive systems.

---

## **Example**

**Typing in a text editor**
* User presses a key
* Character appears almost instantly
* Process must respond within milliseconds

**Clicking a button in a UI**
* User clicks
* Visual feedback (highlight, animation) appears quickly

**Game input**
* Player presses a key
* Character moves immediately
* Delays would break gameplay

---

## **Details**

* Performance measured using [[Response Time]]
* Often uses:
  * [[RR Scheduling|Round-Robin Scheduling]]
  * [[MLF Scheduling|Multilevel Feedback Queues]]
* Competes with other processes for CPU time

Challenges:

* Maintaining responsiveness under heavy load
* Balancing fairness with performance

Key characteristic:

* Short bursts of CPU usage followed by waiting for user input

---

## **Related**

* [[Preemptive Scheduling]]
* [[Response Time]]
* [[RR Scheduling]]
* [[MLF Scheduling]]
* [[Time Quantum]]

---

## **One Line Recall**

An interactive process constantly communicates with the user and must respond quickly to every input.