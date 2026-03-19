---
aliases:
  - RL
---
## **Quick Summary**
The ready list is the set of processes that are ready to run and waiting for CPU time.

## **Core Idea**
Processes that are ready but not currently running are placed in the ready list until the scheduler selects one.

## **What it is**
The **Ready List (RL)** is a data structure maintained by the operating system that contains all processes that:

- Are ready to execute
- Are waiting for CPU access

The currently running process is **not** in the ready list.

Processes move in and out of the ready list frequently.

### Processes enter the Ready List when:
- They are created
- They finish waiting for a resource
- They finish I/O operations

### Processes leave the Ready List when:
- They begin running
- They become blocked waiting for a resource

## How its Used
The [[Process Scheduler|Scheduler]] selects the next process to run from the ready list.

Many systems organize the ready list by **priority**.

The scheduler typically chooses:
```
highest [[Process Priority|priority]] process in RL
```

## **Example**

Ready List:
```
RL = [P2, P3, P4]
```

Scheduler selects:
```
P2
```

P2 becomes the running process.

If P2 requests a busy resource:
- P2 → blocked
- Removed from RL
- Added to [[Waiting List]]

## **Details**

### Priority Scheduling
If the ready list is priority-based:
```
P3 (priority 3)
P2 (priority 2)
P1 (priority 1)
```

The scheduler selects **P3 first**.

### Interaction with Resources
Processes move between lists frequently:
```
Ready List → Running → Waiting List → Ready List
```

## **Related**
[[Process Scheduler]]
[[Resource Request]]
[[Resource Release]]
[[Waiting List]]
[[PCB]]

## **One Line Recall**
The ready list contains all processes ready to run but waiting for CPU scheduling.