---
layout: base
title: "Lecture 4: Multiprogramming Operating System"
date: 2026-06-25 10:30:00 +0530
categories: jekyll update
permalink: "/lecture-4-multiprogramming-operating-system/"
---

# {{ page.title | escape }}

## 1. What is a Multiprogramming Operating System?

A Multiprogramming Operating System is an operating system in which multiple programs (jobs) are loaded into the main memory simultaneously, and the CPU switches among them to maximize CPU utilization.

Unlike a Batch Operating System, where only one job executes at a time, multiprogramming allows several jobs to reside in memory together. When one job waits for I/O, the CPU executes another ready job.

### # Why Was Multiprogramming Introduced?

In early batch systems, the CPU frequently became idle.

Example:

```
Job A
CPU Processing → Read Disk → Wait...
CPU is idle during disk reading.
```

During the waiting period, no useful computation occurs. To improve CPU efficiency, multiprogramming was introduced.

### # Need for Multiprogramming

Multiprogramming addresses several limitations of batch systems:

- Improves CPU utilization.
- Reduces CPU idle time.
- Increases system throughput.
- Allows better sharing of system resources.
- Improves overall system performance.

## Working of a Multiprogramming Operating System

### **Step 1:** Multiple Jobs Loaded

The operating system loads several jobs into RAM.

```
Main Memory

+---------------------+
| Job 1               |
+---------------------+
| Job 2               |
+---------------------+
| Job 3               |
+---------------------+
| Job 4               |
+---------------------+
```

### **Step 2:** CPU Starts Execution

The CPU begins executing Job 1.

```
CPU
↓
Job 1
```

### **Step 3:** Job Requests I/O

Suppose Job 1 needs to read data from the disk.

```
Job 1
↓
Waiting for Disk
```

### **Step 4:** Context Switch

Instead of leaving the CPU idle, the operating system performs a context switch. The CPU begins executing Job 2.

```
CPU
↓
Job 2
```

### **Step 5:** Continue Execution

When Job 1 completes its disk operation, it returns to the Ready Queue. The operating system schedules it again when the CPU becomes available.

## Context Switching

A context switch is the process of saving the current state of a running process and loading the state of another process.

The saved information includes:

- Program Counter (PC)
- CPU Registers
- Stack Pointer
- Process State
- Memory Information

## CPU Scheduling in Multiprogramming

The operating system maintains a Ready Queue containing jobs ready to execute. The CPU Scheduler selects one job at a time.

Popular scheduling algorithms include:

- First Come First Served (FCFS)
- Shortest Job First (SJF)
- Priority Scheduling
- Round Robin (used mainly in time-sharing systems)

## Memory Organization

A multiprogramming system keeps multiple programs in memory simultaneously. Each program occupies a separate memory partition. The operating system ensures that one program cannot overwrite another program's memory.

## States of a Program

- New: The program has been created but is not yet ready to execute.

- Ready: The program is waiting for CPU time.

- Running: The program is currently executing on the CPU.

- Waiting (Blocked): The program is waiting for an I/O operation or another event.

- Terminated: The program has finished execution.

![States of a Program]({{ '/assets/images/States-of-a-Program.png' | relative_url }})

### # Advantages of Multiprogramming

1. High CPU Utilization: The CPU remains busy most of the time.

2. Better Resource Utilization: CPU, memory, and I/O devices are used more efficiently.

3. Increased Throughput: More jobs are completed within a given period.

4. Reduced CPU Idle Time: The CPU executes another job while one waits for I/O.

5. Better Overall Performance: The system performs more work compared to a batch system.

### # Disadvantages of Multiprogramming

1. Complex Operating System: The OS must manage multiple programs simultaneously.

2. Memory Management Complexity: The OS must allocate and protect memory for each program.

3. CPU Scheduling Complexity: Efficient scheduling algorithms are required.

4. Deadlock Possibility: Programs competing for resources may become permanently blocked.

5. Security Challenges: Multiple programs sharing resources require proper protection mechanisms.
