---
layout: base
title: "Lecture 1: Basic Functions and Need of an Operating System"
date: 2026-06-25 10:30:00 +0530
categories: jekyll update
permalink: "/lecture-1-basic-functions-and-need-of-an-operating-system/"
---

# {{ page.title | escape }}

## 1. What is an Operating System?

An Operating System is a program that acts as an intermediary between the user and computer hardware.

Examples of Operating Systems:

- Microsoft Windows
- Linux
- macOS
- Android
- iOS

## 2. Position of Operating System in a Computer System

![Timeline of Microprocessor Evolution]({{ '/assets/images/Position-of-Operating-System-in-a-Computer-System.png' | relative_url }})

## 3. Goals of an Operating System

- **Convenience:**

  The primary goal of an operating system is convenience for the user. If an application program is a set of machine instructions then it is completely responsible for controlling the computer hardware. It is a complicated task. To simplify this task, a set of system programs are provided, called utilities and they implement frequently used functions which assist in program creation, management of files and control of Input/Output devices.

  Example: Instead of manually controlling a printer, we simply click "Print."

- **Efficiency:**

  The secondary goal of an operating system is efficient operation of the system. Operating system is responsible for managing the resources. That is the movement, storage and processing of data.A portion of operating system is in main memory. This includes the Kernel or nucleus, which contains the most frequently used functions in the operating system. The remainder of main memory contains other user programs and data. Operating system determine how much processor time is to be devoted to the execution of a program. That is the efficient utilization of the resources.

  Example: Several applications can share CPU time.

- **Ability to Evolve:**

  Operating system should be constructed in such a way as to permit the effective development, testing, and introduction of new system functions.

  Operating system will evolve over time for a number of reasons:
  - Hardware upgrades plus new types of hardware. For example, view several applications at the same time through windows.
  - New services, that is new measurement and control tools may be added.
  - Fixes, that is faults will be discovered and fixes.

  Example: Modern Windows versions support touch screens, Wi-Fi, Bluetooth, etc.

## 4. Functions of an Operating System

### i. Processor Management

OS decides which process gets the processor when and how much time. This function is called process scheduling. Operating System does the following activities for processor management.

- Keeps tracks of processor and status of process. Program responsible for this task is known as traffic controller.
- Allocates the processor(CPU) to a process.
- De-allocates processor when processor is no longer required.

### ii. Memory Management

Memory management refers to management of Primary Memory or Main Memory. Main memory is a large array of words or bytes where each word or byte has its own address.

Main memory provides a fast storage that can be access directly by the CPU. So for a program to be executed, it must in the main memory. Operating System does the following activities for memory management.

- Keeps tracks of primary memory i.e. what part of it are in use by whom, what part are not in use.
- In multiprogramming, OS decides which process will get memory when and how much.
- Allocates the memory when the process requests it to do so.
- De-allocates the memory when the process no longer needs it or has been terminated.

### iii. Device Management

OS manages device communication via their respective drivers. Operating System does the following activities for device management.

- Keeps tracks of all devices. Program responsible for this task is known as the I/O controller.
- Decides which process gets the device when and for how much time.
- Allocates the device in the efficient way.
- De-allocates devices.

### iv. File Management

A file system is normally organized into directories for easy navigation and usage. These directories may contain files and other directions. Operating System does the following activities for file management.

- Keeps track of information, location, uses, status etc. The collective facilities are often known as file system.
- Decides who gets the resources.
- Allocates the resources.
- De-allocates the resources.

### v. User Interface

The user interface (UI) is what users interact with when using a computer. The OS provides:

- Graphical User Interfaces (GUIs): Offers visual elements like windows, icons, and menus.
- Command-Line Interfaces (CLIs): Allows text-based commands for more control.

A user-friendly UI makes it easier for users to navigate the system and manage files and applications efficiently.

### vi. Error Detection and Handling

The OS continuously monitors the system for errors. It manages:

- Error detection: Identifies hardware and software errors.
- Error handling: Takes corrective actions to fix issues.
- Logging: Records errors for future analysis.

By detecting and handling errors, the OS maintains system stability and prevents crashes.

### vii. Security and Access Control

Security and access control protect the system and data. The OS implements:

- User authentication: Verifies user identities using passwords or biometrics.
- Access permissions: Controls who can access or modify files and resources.
- Security measures: These include encryption, firewalls, and antivirus programs.

The OS monitors system activities for suspicious behaviour and enforces security policies. This ensures data integrity and system security, protecting against unauthorised access and threats.
