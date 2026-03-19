## **Quick Summary**
The execution stack (or call stack) is a memory structure that stores function calls, local variables, and return addresses for a running [[thread]].

---

## **Core Idea**

* Each [[thread]] needs its own execution stack so it can keep track of its own function calls and temporary data during execution.

---

## **What it is**

The **Execution Stack** is a region of memory used during program execution to store information about active function calls.

Each entry in the stack is called a **stack frame** and typically contains:

* Local variables
* Function parameters
* Return address
* Saved register values

Stacks operate using **Last-In, First-Out (LIFO)** behavior:

* New function calls are **pushed onto the stack**
* When functions return, their frames are **popped off the stack**

In a **multithreaded process**, each thread has its **own private execution stack** while sharing other resources like:

* Code
* Global variables
* Open files

This separation ensures that threads can execute independently without corrupting each other's runtime data.

---

## **How its Used**

Execution stacks are used whenever:

* Functions are called
* Recursive functions execute
* Local variables are allocated

They are essential for:

* Managing nested function calls
* Keeping track of execution flow
* Allowing multiple threads to execute independently

Every [[thread]] must maintain its own stack to store its local execution state and prevent interference with other threads.

---

## **Example**

### Function Call Example
```
main()
├── funcA()
│    └── funcB()
```

Stack during execution of `funcB`:
```
| funcB stack frame |
| funcA stack frame |
| main stack frame  |
```

When `funcB` finishes:

* Its frame is removed
* Execution returns to `funcA`

### Multithreaded Example

Thread 1 stack:
```
| process_data() |
| main()         |
```

Thread 2 stack:
```
| receive_input() |
| main()          |
```

Both threads share the same program but maintain **separate stacks**.

---

## **Details**

### Stack Pointer (SP)

The **stack pointer** tracks the current top of the stack.

### Stack Frames

Each frame contains the runtime data for a single function call.

### Stack Overflow

Occurs when too many stack frames are allocated (often due to deep recursion).

---

## **Related**

* [[Thread]]
* [[Thread Control Block]]
* [[Program Counter]]
* [[Process Control Block]]

---

## **One Line Recall**

The execution stack stores function calls and runtime data for a thread using a LIFO structure.