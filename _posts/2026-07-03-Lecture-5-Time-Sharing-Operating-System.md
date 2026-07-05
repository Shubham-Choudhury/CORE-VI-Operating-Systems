---
layout: base
title: "Lecture 5: Time-Sharing Operating System"
date: 2026-06-25 10:30:00 +0530
categories: jekyll update
permalink: "/lecture-5-time-sharing-operating-system/"
---

# {{ page.title | escape }}

## 1. What is a Time-Sharing Operating System?

A Time-Sharing Operating System is an operating system in which the CPU time is divided into small time intervals called time slices (time quanta), allowing multiple users or multiple processes to share the CPU interactively.

Each process gets a fixed amount of CPU time. If it does not finish within that time, it is temporarily paused, and the CPU is assigned to another process.

## 2. Why Was Time-Sharing Introduced?

Multiprogramming systems focused mainly on efficient CPU utilization, high throughput.

However, they had limitations: slow user response, poor interactivity, users often waited a long time

Time-sharing was introduced to provide:

- Fast response time
- Interactive computing
- Fair CPU allocation
- Simultaneous access for multiple users

## 3. What is Interactive Computing?

Interactive computing allows users to communicate directly with the computer while programs are running. Users receive immediate feedback after each action.

Examples:

- Typing in a text editor
- Browsing the Internet
- Online banking
- Editing a spreadsheet
- Writing code in an IDE

## 4. Concept of Time Slice (Time Quantum)

A time slice or time quantum is the maximum amount of CPU time allocated to a process before the CPU switches to another process. The exact value depends on the operating system.

## 5. Working of a Time-Sharing Operating System

### **Step 1:** Multiple Users Submit Requests

Several users log in simultaneously.

Example:

```
User A → Editing a file
User B → Browsing
User C → Printing
User D → Running calculations
```

### **Step 2:** Processes Enter the Ready Queue

The OS stores all ready processes in a queue.

```
Ready Queue

P1
P2
P3
P4
```

### **Step 3:** CPU Executes One Process

The scheduler selects P1. P1 runs for the allocated time quantum.

### **Step 4:** Time Quantum Expires

If P1 is not finished:

- Its current state is saved.
- It moves to the end of the ready queue.
- P2 begins execution.

### **Step 5:** Continuous Rotation

The CPU keeps rotating among processes. Every process receives CPU time repeatedly until it completes.

```
P1 → P2 → P3 → P4 → P1 → P2 → ...
```
### # Advantages of Time-Sharing Operating Systems

1. Fast Response Time: Users receive quick responses to their actions.

2. Multi-User Support: Many users can access the system simultaneously.

3. Efficient CPU Utilization: The CPU remains busy most of the time.

4. Fair Resource Sharing: Every process receives CPU time.

5. Improved Productivity: Users can work interactively without waiting for long periods.

### # Disadvantages of Time-Sharing Operating Systems

1. Frequent Context Switching: Frequent switching increases system overhead.

2. Security Challenges: Multiple users require strong authentication and access control.

3. Higher Memory Requirement: Many processes must remain in memory.

4. Complex Scheduling: The scheduler must efficiently manage many users and processes.

5. Performance Degradation: Too many users can slow down the system.