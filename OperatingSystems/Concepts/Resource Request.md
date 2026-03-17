## **Quick Summary**
A resource request occurs when a process asks the operating system for access to a resource.

## **Core Idea**
If the resource is available, the OS allocates it.
If the resource is unavailable, the requesting process is blocked and placed on a waiting list.

## **What it is**
A **resource request** happens when a process needs access to a resource to continue execution.

The process calls a system function:
```
request(r)
```

Where:
- `r` = requested resource

The OS then checks the resource's [[Resource Control Block (RCB)]].

### Case 1: Resource is free
- Resource state becomes **allocated**
- The resource is added to the process's list of resources

### Case 2: Resource is not free
- The process is **blocked**
- The process's [[PCB]] is moved from the [[Ready List]] to the resource's [[Waiting List]]
- The [[Process Scheduler|Scheduler]] selects another process to run

## How its Used
Resource requests occur constantly in operating systems.

Examples include:
- Requesting disk access
- Requesting a printer
- Requesting memory buffers
- Requesting database locks

Without this mechanism, multiple processes could try to use the same resource simultaneously.

## **Example**

### Printer Request

Processes:
```
P1 running
P2 ready
P3 ready
```

P1 requests the printer.

**Case A: Printer free**
- Printer → allocated to P1

**Case B: Printer busy**
- P1 → blocked
- P1 → added to printer waiting list
- Scheduler chooses another process

## **Details**

### Request Function
```python
request(r):
    if r.state == free:
        r.state = allocated
        insert r into self.other_resources
    else:
        self.state = blocked
        move self from RL to r.waiting_list
        scheduler()
```

Key actions:
- Check availability
- Allocate resource or block process
- Possibly trigger scheduling

## **Related**
[[Resource]]
[[Resource Release]]
[[Resource Control Block (RCB)]]
[[Waiting List]]
[[Ready List]]
[[Process Scheduler]]

## **One Line Recall**
A resource request is when a process asks the OS for a resource, receiving it if available or blocking if not.