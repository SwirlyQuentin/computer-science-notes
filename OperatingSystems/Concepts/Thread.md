## **Quick Summary**

A thread is an independent path of execution within a process.

---

## **Core Idea**

* Threads allow multiple tasks within a program to run concurrently while sharing the same process resources.

---

## **What it is**

A **Thread** is a lightweight unit of execution within a process.

Instead of creating multiple processes, programs can create multiple threads that share:

* Program code
* Global variables
* Open files
* System resources

However, each thread maintains its own:

* [[Program counter]]
* [[Execution stack]]
* CPU state

This allows threads to execute different instructions independently.

Threads are more efficient than processes because they do not require duplicating the entire process environment.

---

## **How its Used**

Threads are used to allow **concurrent activities within applications**.

Common uses include:

* Background tasks
* Parallel computation
* Responsive user interfaces
* Network servers

Threads are especially important in applications where tasks may block waiting for resources.

---

## **Example**

### Web Browser

* One thread downloads data from the internet
* Another thread draws images on the screen

Both happen simultaneously.

### Internet Server

* Receives many user requests
* Creates a thread for each request

This allows many users to be served concurrently.

### Word Processor

Threads can run spell checking and handle user typing at the same time.

---

## **Details**

### Thread Independence

Each thread has its own [[program counter]] and stack, but shares process resources.

### Efficiency

Threads are cheaper to create and switch than processes.

---

## **Related**

* [[Multithreading]]
* [[Thread Control Block]]
* [[Execution Stack]]
* [[Program Counter]]

---

## **One Line Recall**

A thread is a lightweight unit of execution inside a process.