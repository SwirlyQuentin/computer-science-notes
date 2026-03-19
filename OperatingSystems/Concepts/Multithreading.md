## **Quick Summary**

Multithreading is the ability of a process to run multiple threads concurrently.

---

## **Core Idea**

* Multiple threads execute different parts of a program simultaneously within the same process.

---

## **What it is**

**Multithreading** is a programming and operating system technique where multiple threads execute within a single process.

Each thread has its own:

* Program counter
* Execution stack
* CPU state

But shares the process's:

* Code
* Global data
* Resources
* Open files

This allows programs to perform multiple tasks at once.

---

## **How its Used**

Multithreading is widely used in modern applications such as:

**Web browsers:**
* One thread downloads data
* One thread renders images

**Word processors:**
* One thread handles typing
* One thread performs spell checking

**Internet servers:**
* Each client request runs in its own thread

---

## **Example**

### Browser Example

* Thread 1: Download webpage data
* Thread 2: Render page graphics
* Thread 3: Handle user input

All run concurrently.

### Parallel CPU Example

If a system has **4 CPUs**:
```
Thread 1 → CPU 1
Thread 2 → CPU 2
Thread 3 → CPU 3
Thread 4 → CPU 4
```

Tasks can run in parallel.

---

## **Details**

### Benefits

* Better CPU utilization
* Faster applications
* Improved responsiveness

### Shared Resources

Threads must carefully synchronize access to shared data to avoid errors.

---

## **Related**

* [[Thread]]
* [[User-Level Threads]]
* [[Kernel-Level Threads]]
* [[Thread Control Block]]

---

## **One Line Recall**

Multithreading allows multiple threads to execute concurrently within the same process.