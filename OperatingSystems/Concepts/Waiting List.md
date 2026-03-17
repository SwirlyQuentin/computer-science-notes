---
aliases:
  - WL
---

## **Quick Summary**
A waiting list is a list of processes that are blocked while waiting for a specific resource.

## **Core Idea**
If a resource is unavailable, processes requesting it cannot continue execution and must wait until the resource becomes free.

## **What it is**
A **waiting list** is a queue associated with a resource.

It stores processes that:
- Requested the resource
- Could not obtain it because it was already allocated

The waiting list is stored inside the [[Resource Control Block (RCB)]].

When a process requests a busy resource:

1. The process becomes **blocked**
2. The process is removed from the [[Ready List]]
3. The process is added to the resource's waiting list

## How its Used
Waiting lists allow the OS to:

- Track which processes need a resource
- Wake processes when resources become available
- Allocate resources fairly

Each resource may have its **own waiting list**.

## **Example**

Printer resource:
```
Waiting List:
P2
P3
P4
```

When P1 releases the printer:

- P2 receives the resource
- P2 moves to the [[Ready List]]

## **Details**

### FIFO Behavior
Most systems treat waiting lists as **FIFO queues**:

First process to request → first to receive resource.

### Relationship with Scheduling
When a process leaves the waiting list:
- It moves to the [[Ready List]]
- The [[Process Scheduler|Scheduler]] may run it.

## **Related**
[[Resource]]
[[Resource Request]]
[[Resource Release]]
[[Resource Control Block (RCB)]]
[[Ready List]]
[[Process Scheduler]]

## **One Line Recall**
A waiting list stores blocked processes waiting for a resource to become available.