---
aliases:
  - Resource Control Block
  - RCB
---
## **Quick Summary**
A Resource Control Block (RCB) is a data structure used by the operating system to represent and manage a resource.

## **Core Idea**
Just like processes are represented by a [[PCB]], resources are represented by **RCBs** so the OS can track their state, availability, and waiting processes.

## **What it is**
A **Resource Control Block (RCB)** is the operating system's internal data structure used to store information about a resource.

The exact structure varies between operating systems, but it typically contains:

- resource_description
- state
- waiting_list

### resource_description
Describes the properties and capabilities of the resource.

Examples:
- Device type
- Resource ID
- Number of units

### state
Indicates whether the resource is available.

Two common cases:

**Single unit resource**
- state = free
- state = allocated

**Multiple unit resource**
- state tracks how many units are:
  - allocated
  - free

### waiting_list
A list of processes waiting for the resource.

If a process requests the resource and it is unavailable:
- The process is removed from the [[Ready List]]
- The process is added to the resource's **waiting list**

## How its Used
RCBs allow the OS to:

- Track resource ownership
- Manage waiting processes
- Allocate resources fairly
- Prevent conflicts

When a process calls [[Resource Request]]:
- The OS checks the RCB

When a process calls [[Resource Release]]:
- The OS updates the RCB and wakes waiting processes.

## **Example**

### Printer Example

RCB for a printer:
```
RCB (Printer)
resource_description: Printer Device
state: allocated
waiting_list: [Process B, Process C]
```

Process A currently has the printer.

Processes B and C are waiting.

When A releases the printer:
- Process B receives it
- B moves to the [[Ready List]]

## **Details**

### Similarity to PCB

| Structure | Purpose |
|-----------|---------|
| [[PCB]] | Represents a process |
| RCB | Represents a resource |

The OS uses both structures together to manage system execution.

## **Related**
[[Resource]]
[[Resource Request]]
[[Resource Release]]
[[Waiting List]]
[[Ready List]]
[[PCB]]

## **One Line Recall**
An RCB is the OS data structure that stores information about a resource and the processes waiting to use it.