---
layout: base
title: "Lecture 9: Comparison of Different Types of Operating Systems"
date: 2026-06-25 10:30:00 +0530
categories: jekyll update
permalink: "/lecture-9-comparison-of-different-types-of-operating-systems/"
---

# {{ page.title | escape }}

## 1. Overview of Operating System Types

![Overview of Operating System Types]({{ '/assets/images/Overview-of-Operating-System-Types.png' | relative_url }})

## 2. Comparison Table

| Feature              | Batch OS          | Multiprogramming OS | Time-Sharing OS       | PC OS        | Workstation OS           | RTOS                        |
| -------------------- | ----------------- | ------------------- | --------------------- | ------------ | ------------------------ | --------------------------- |
| User Interaction     | None              | Very Limited        | High                  | High         | High                     | Usually Limited             |
| CPU Utilization      | Moderate          | High                | High                  | High         | Very High                | Very High                   |
| Response Time        | Slow              | Moderate            | Fast                  | Fast         | Fast                     | Deterministic               |
| Number of Users      | Many (indirectly) | Multiple jobs       | Multiple users        | Single user  | Single professional user | Depends on application      |
| Scheduling           | FCFS              | FCFS, SJF, Priority | Round Robin           | Various      | Various                  | Priority-based              |
| Main Goal            | High throughput   | Maximize CPU use    | Interactive computing | Ease of use  | High performance         | Meet deadlines              |
| Typical Applications | Payroll, billing  | Server processing   | Computer labs         | Home, office | Engineering, AI          | Medical, industrial control |
