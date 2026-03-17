## **Quick Summary**
A resource release occurs when a process finishes using a resource and returns it to the operating system.

## **Core Idea**
When a resource is released, the OS either:
- Marks the resource as free, or
- Allocates it to the next waiting process.

## **What it is**
A **resource release** happens when a process calls:
```
release(r)
```

Where:
- `r` = resource being released.

The operating system updates the resource's [[Resource Control Block (RCB)]].

### Case 1: Waiting list empty
- Resource state becomes **free**
- Current process continues execution

### Case 2: Waiting list not empty
- The first process in the [[Waiting List]] gets the resource
- That process moves to the [[Ready List]]
- The [[Process Scheduler|Scheduler]] decides which process runs next

## How its Used
Releasing resources ensures:

- Resources are reused efficiently
- Waiting processes can continue
- System performance remains high

Without releasing resources, the system would quickly run out of available resources.

## **Example**

Printer resource:
```
Waiting list: [P2, P3]
```

Process P1 releases the printer.

Result:
- P2 receives the printer
- P2 moves to the [[Ready List]]

Scheduler decides whether:
- P1 continues
- P2 runs next

## **Details**

### Release Function
```python
release(r):
    remove r from self.other_resources
    if r.waiting_list == empty:
        r.state = free
    else:
        remove q from head of r.waiting_list
        insert r into q.other_resources
        q.process_state = ready
        move q from r.waiting_list to RL
        scheduler()
```

Key actions:
- Remove resource from current process
- Assign it to next waiting process
- Possibly trigger scheduling

## **Related**
[[Resource]]
[[Resource Request]]
[[Resource Control Block (RCB)]]
[[Waiting List]]
[[Ready List]]
[[Process Scheduler]]

## **One Line Recall**
A resource release returns a resource to the OS so it can be reused or allocated to waiting processes.