---
layout: base
title: "Lecture 7: Process Control Operating Systems (Process Concept and Process Management)"
date: 2026-06-25 10:30:00 +0530
categories: jekyll update
permalink: "/lecture-7-process-control-operating-systems/"
---

# {{ page.title | escape }}

## 1. What is a Process?

A Process is a program that is currently being executed.

A program stored on a disk is only a collection of instructions. When the operating system loads it into memory and starts execution, it becomes a process.

```
Program + Execution = Process
```

### # Program vs Process

| Program                    | Process                  |
| -------------------------- | ------------------------ |
| Passive entity             | Active entity            |
| Stored on disk             | Loaded into memory       |
| Does not execute by itself | Executes instructions    |
| Static                     | Dynamic                  |
| Example: MS Word installer | Example: Running MS Word |

#### **Example:**

Suppose you have a file named Calculator.exe.

- Stored on the disk → Program
- Double-click and it starts running → Process

## 2. What is Process Control?

Process Control refers to the activities performed by the operating system to manage processes. The operating system continuously monitors all active processes.

These activities include:

- Creating processes
- Scheduling processes
- Suspending processes
- Resuming processes
- Synchronizing processes
- Terminating processes

### # Why is Process Control Necessary?

Without process control:

- Applications would interfere with each other.
- CPU time would not be shared fairly.
- The computer could become unstable.
- Process control ensures that every process gets the resources it needs.

## 3. Components of a Process

A process consists of several parts:

![Components of a Process]({{ '/assets/images/Components-of-a-Process.png' | relative_url }})

1.  Program Code (Text Section): Contains executable instructions.

    Example:

    ```c
    printf("Hello World");
    ```

2.  Data Section: Stores global variables, static variables

    Example:

    ```c
    int total = 100;
    ```

3.  Heap: Used for dynamic memory allocation. Memory is allocated during program execution.

    Example:

    ```c
    malloc()
    new
    ```

4.  Stack: Stores function calls, local variables, return addresses. Every function call creates a new stack frame.

## 4. Process States (Life Cycle)

![Process States (Life Cycle)]({{ '/assets/images/Process-Life-Cycle.png' | relative_url }})

## 5. Process State Transitions

- New → Ready: Process is admitted.
- Ready → Running: CPU scheduler selects it.
- Running → Waiting: Process requests I/O.
- Waiting → Ready: I/O completes.
- Running → Terminated: Execution finishes.

## 6. Process Control Block (PCB)

The Process Control Block (PCB) is a data structure maintained by the operating system that stores all important information about a process. The PCB allows the OS to pause and resume processes correctly.

### # Information Stored in PCB

| Field                  | Description                     |
| ---------------------- | ------------------------------- |
| Process ID (PID)       | Unique identifier               |
| Process State          | Ready, Running, Waiting, etc.   |
| Program Counter        | Address of next instruction     |
| CPU Registers          | Current register values         |
| Memory Information     | Memory allocated to the process |
| Scheduling Information | Priority, queue details         |
| I/O Status             | Devices currently in use        |
| Accounting Information | CPU time, user ID, etc.         |

### # PCB Structure

![PCB Structure]({{ '/assets/images/PCB-Structure.png' | relative_url }})

## 7. Process Creation

A new process may be created when:

- A user starts an application.
- Another process creates it.
- The operating system starts background services.
- The system boots.

### # Steps

- Assign Process ID (PID)
- Allocate memory
- Create PCB
- Load program into memory
- Add process to Ready Queue

## 8. Process Termination

A process terminates when:

- It completes normally.
- The user closes it.
- A fatal error occurs.
- The operating system terminates it.

After termination:

- Memory is released.
- Files are closed.
- PCB is removed.
- CPU resources become available.

## 9. Process Scheduling

Many processes compete for CPU time. The CPU Scheduler decides which process executes next. Scheduling improves CPU utilization and system performance.

## 10. Context Switching

When the CPU switches from one process to another:

1. Current process information is saved in its PCB.
2. Next process information is loaded from its PCB.
3. CPU resumes execution.
