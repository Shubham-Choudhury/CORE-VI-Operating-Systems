---
layout: base
title: "Lecture 3: Types of Operating Systems – Batch Operating System and Multiprogramming Operating System"
date: 2026-06-25 10:30:00 +0530
categories: jekyll update
permalink: "/lecture-3-types-of-operating-systems-batch-operating-system-and-multiprogramming-operating-system/"
---

# {{ page.title | escape }}

## 1. Evolution of Operating Systems

| Generation                       | Operating System Type                                              |
| -------------------------------- | ------------------------------------------------------------------ |
| First Generation (1940–1955)     | No Operating System                                                |
| Second Generation (1955–1965)    | Batch Operating System                                             |
| Third Generation (1965–1980)     | Multiprogramming Operating System                                  |
| Fourth Generation (1980–Present) | Time-Sharing, Personal Computer, Real-Time, Distributed, Mobile OS |

Initially, computers had no operating system. Users interacted directly with hardware, making operation difficult and time-consuming. To solve this problem, the Batch Operating System was introduced.

## 2. What is a Batch Operating System?

A Batch Operating System is an operating system in which similar jobs are collected, grouped into batches, and executed automatically one after another without user interaction during execution.

### # Key Idea:

- Jobs are submitted.
- Jobs are grouped.
- The operating system processes them sequentially.
- Users do not interact with the computer while the jobs are running.

## Why Was Batch Processing Introduced?

### # Early computers were:

- Very expensive
- Slow
- Limited in memory
- Operated manually

### # Users had to:

- Load programs manually
- Set switches
- Mount tapes
- Wait until execution completed

This wasted valuable CPU time.

### # Batch processing was introduced to:

- Reduce idle CPU time
- Improve system utilization
- Automate job execution
- Increase throughput

### # What is a Job?

A job is a unit of work submitted to the operating system.

## Working of a Batch Operating System

### **Step 1:** Job Submission

Users submit their programs to the computer operator.

Example:

- Student Result Processing
- Salary Calculation
- Fee Report Generation

### **Step 2:** Job Collection

The operator groups similar jobs together.

Example Batch:

```
Batch 1
---------
Job 1 : Student Results
Job 2 : Student Results
Job 3 : Student Results
Job 4 : Student Results
```

### **Step 3:** Job Queue

The operating system stores jobs in a queue.

```
-------------------------
Job Queue

Job A
Job B
Job C
Job D
-------------------------
```

Jobs wait until the CPU becomes available.

### **Step 4:** Automatic Execution

The operating system executes:

```
Job A
↓
Job B
↓
Job C
↓
Job D
```

No human intervention is required during execution.

### **Step 5:** Output Generation

After execution:

- Reports are printed.
- Results are stored.
- Users collect the output later.

## Batch Operating System Architecture

![Batch Operating System Architecture]({{ '/assets/images/Batch-Operating-System-Architecture.png' | relative_url }})

## Characteristics of Batch Operating Systems

1. No User Interaction: Once jobs start executing, users cannot interact with them.

2. Similar Jobs are Grouped: Jobs with similar requirements are executed together.

3. Sequential Processing: Jobs are executed one after another.

4. High Throughput: Many jobs can be processed efficiently.

5. Long Waiting Time: Users may wait hours before receiving output.

## Advantages of Batch Operating Systems

1. High CPU Utilization: CPU remains busy most of the time.

2. Reduced Idle Time: Jobs execute continuously.

3. Efficient for Large Volumes: Suitable for processing thousands of jobs.

4. Less Manual Intervention: The operator loads jobs once. Execution becomes automatic.

5. Better Throughput: Many jobs are completed in less total time.

## Disadvantages of Batch Operating Systems

1. No User Interaction: Users cannot communicate with the program during execution.

2. Long Waiting Time: A job may wait a long time before execution.

3. Difficult Debugging: If one job fails, identifying the error can be difficult.

4. No Immediate Response: Results are available only after all processing is complete.

5. Job Priority is Limited: Urgent jobs may have to wait behind earlier submitted jobs.


## 2. What is a Multiprogramming Operating System?

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
