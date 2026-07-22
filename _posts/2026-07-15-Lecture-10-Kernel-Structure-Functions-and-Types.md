---
layout: base
title: "Lecture 10: Kernel: Structure, Functions, and Types"
date: 2026-06-25 10:30:00 +0530
categories: jekyll update
permalink: "/lecture-10-kernel-structure-functions-and-types/"
---

# {{ page.title | escape }}

## 1. What is a Kernel?

The Kernel is the core (central) component of an Operating System. It acts as a bridge between Applications and Hardware. The kernel manages CPU, Memory, Input/Output devices, File system, Processes Without the kernel, an operating system cannot function.

$$\text{Kernel} = \text{Heart of the Operating System}$$

## 2. Position of Kernel in an Operating System

![Position of Kernel in an Operating System]({{ '/assets/images/Position-of-Kernel-in-an-Operating-System.png' | relative_url }})

## 3. Major Functions of the Kernel

### # Function 1: Process Management

The kernel Creates processes, Terminates processes, Schedules CPU time, Performs context switching.

### # Function 2: Memory Management

The kernel manages RAM. Responsibilities include Allocate memory, Deallocate memory, Protect memory, Support virtual memory.

### # Function 3: Device Management

The kernel communicates with Keyboard, Mouse, Monitor, SSD, Printer Scanner. It uses device drivers.

### # Function 4: File System Management

The kernel performs File creation, File deletion, Reading, Writing, Directory management.

### # Function 5: Interrupt Handling

Hardware generates interrupts. The kernel immediately responds.

### # Function 6: Security and Protection

The kernel ensures User authentication, Memory protection, Process isolation, Permission checking.

### # Function 7: Input/Output Management

The kernel controls Disk access, Network communication, USB devices, Printers, Audio devices.

## Types of Kernel

There are four major kernel architectures.

<ol type = "I">
<li>Monolithic Kernel</li>
<li>Microkernel</li>
<li>Hybrid Kernel</li>
<li>Modular Kernel</li>
</ol>

## I. Monolithic Kernel

A Monolithic Kernel contains all operating system services inside one large kernel. Services include Memory management, File system, Device drivers, CPU scheduling, Networking. Everything runs in Kernel Mode.

### # Architecture

![Monolithic Kernel Architecture]({{ '/assets/images/Monolithic-Kernel-Architecture.png' | relative_url }})

### # Advantages

- High performance
- Fast communication
- Efficient execution

### # Disadvantages

- Large kernel size
- Difficult maintenance
- A bug in one component can crash the entire system

#### Examples: Linux, Traditional UNIX systems

## II. Microkernel

A Microkernel keeps only essential services inside the kernel. Other services run in User Mode. Kernel contains CPU scheduling, Memory management, Inter-process communication (IPC). Services such as file systems and device drivers execute outside the kernel.

### # Architecture

![Microkernel Architecture]({{ '/assets/images/Microkernel-Architecture.png' | relative_url }})

### # Advantages

- Better security
- Better reliability
- Easier maintenance
- Fault isolation

### # Disadvantages

- More communication overhead
- Lower performance compared to monolithic kernels

### # Examples; MINIX 3, QNX

## III. Hybrid Kernel

A Hybrid Kernel combines features of Monolithic and Microkernel architectures. Some services run in Kernel Mode for speed, while others run in User Mode for reliability.

### # Architecture

![Hybrid Kernel Architecture]({{ '/assets/images/Hybrid-Kernel-Architecture.png' | relative_url }})

### # Advantages

- Good performance
- Better stability than monolithic kernels
- Flexible design

### # Disadvantages

- More complex architecture
- Larger than a microkernel

### # Examples: Microsoft Windows NT, macOS (uses the XNU hybrid kernel)

## IV. Modular Kernel

A Modular Kernel allows additional components to be loaded or removed as modules while the system is running. Modules can be added without recompiling the kernel.

![Modular Kernel]({{ '/assets/images/Modular-Kernel.png' | relative_url }})

### # Advantages
- Flexible
- Easy to update
- Better performance than a pure microkernel
- Easier maintenance

### # Disadvantages
- Module compatibility must be managed
- More complex than a simple monolithic design

### # Example: Modern Linux supports Loadable Kernel Modules (LKMs).