---
layout: base
title: "Lecture 11: Processor Modes and User Modes"
date: 2026-06-25 10:30:00 +0530
categories: jekyll update
permalink: "/lecture-11-processor-modes-and-user-modes/"
---

# {{ page.title | escape }}

## 1. What is Processor Mode?

A Processor Mode is the operating state of the CPU that determines what instructions the currently executing program is allowed to perform.

The processor operates mainly in two modes:

<ol type="I">
<li>User Mode</li>
<li>Kernel Mode</li>
</ol>

![Processor Mode]({{ '/assets/images/Processor-Mode.png' | relative_url }})

## I. User Mode

User Mode is the restricted execution mode in which normal application programs execute. Applications cannot directly access hardware resources.

Examples of Programs Running in User Mode: Web Browser, Text Editor, Music Player, Calculator, Video Player, Games. These applications must request services from the operating system.

Characteristics of User Mode

- Limited privileges
- Cannot directly access hardware
- Cannot modify operating system memory
- Cannot execute privileged instructions
- More secure

![User Mode Diagram]({{ '/assets/images/User-Mode-Diagram.png' | relative_url }})

## II. Kernel Mode

Kernel Mode is the privileged execution mode in which the operating system executes. The kernel has complete control over the computer.

Characteristics

- Full hardware access
- Executes privileged instructions
- Manages memory
- Schedules CPU
- Controls devices
- Handles interrupts
- Executes system calls

Examples of Kernel Activities: Allocating memory, Reading disk blocks, Handling keyboard interrupts, Scheduling processes, Managing network communication

## 2. Privileged Instructions

A privileged instruction is an instruction that can only be executed in Kernel Mode. If a user program attempts to execute it, the CPU generates an exception (trap).

Examples: Shut down CPU, Enable/Disable interrupts, Modify page tables, Access I/O ports, Configure hardware, Change processor mode

## 3. Non-Privileged Instructions

These instructions are safe for application programs.

Examples: Addition, Subtraction, Multiplication, Division, Variable assignment, Conditional statements, Function calls

## 4. Mode Bit

Modern processors maintain a Mode Bit (or privilege bit). The CPU checks this bit before executing sensitive instructions.

Example: Mode Bit = 0 -> Kernel Mode; Mode Bit = 1 -> User Mode

### # Mode Switching

The CPU switches between User Mode and Kernel Mode whenever privileged services are required.

![Mode Switching]({{ '/assets/images/Mode-Switching.png' | relative_url }})

### # Why Are Two Modes Necessary?

Without processor modes any program could damage the OS, any application could access another user's files, viruses would easily control the computer, hardware could be misused.

Two execution modes improve Security, Stability, Reliability, Controlled hardware access

## Advantages of User and Kernel Modes

- Protects the operating system
- Prevents unauthorized hardware access
- Improves security
- Prevents accidental crashes
- Enables multitasking safely
- Supports multi-user systems

## Disadvantages of User and Kernel Modes

- Mode switching introduces small overhead.
- More complex operating system design.
- Frequent system calls can slightly reduce performance.

![Kernel Modes Architecture Diagram]({{ '/assets/images/Kernel-Modes-Architecture-Diagram.png' | relative_url }})
