---
layout: base
title: "Lecture 11: System Calls"
date: 2026-06-25 10:30:00 +0530
categories: jekyll update
permalink: "/lecture-11-system-calls/"
---

# {{ page.title | escape }}

## 1. What is a System Call?

A System Call is a mechanism through which a user program requests a service from the operating system kernel. It acts as an interface between User Programs and Operating System.

$$\text{System Call} = \text{Request made by a program to the Operating System.}$$

### # Position of System Calls

![Position of System Calls]({{ '/assets/images/Position-of-System-Calls.png' | relative_url }})

## 2. Types of System Calls

### # Type 1: Process Control

Used to create and manage processes.

### # Type 2: File Management

Used for file operations. Operations include Create file, Delete file, Open file, Close file, Read file, Write file, Rename file.

### # Type 3: Device Management

Used to communicate with hardware devices.

### # Type 4: Information Maintenance

Used to obtain or modify system information.

### # Type 5: Communication

Allows processes to communicate.

### # Type 6: Protection

Used for security.

## 3. Common UNIX/Linux System Calls

| System Call | Purpose                |
| ----------- | ---------------------- |
| open()      | Open file              |
| read()      | Read file              |
| write()     | Write file             |
| close()     | Close file             |
| fork()      | Create process         |
| exec()      | Execute program        |
| wait()      | Wait for child process |
| exit()      | Terminate process      |
| getpid()    | Get Process ID         |

## 4. Common Windows API Functions

Windows applications use the Windows API, which internally invokes system calls. Examples include CreateFile(), ReadFile(), WriteFile(), CloseHandle(), CreateProcess().

### # Advantages of System Calls
- Secure hardware access
- Protect operating system
- Easy programming
- Hardware independence
- Standard interface
- Better resource management

### # Disadvantages of System Calls
- Mode switching overhead
- Slower than direct function calls
- Kernel complexity
- More CPU instructions

## 5. Difference Between Function Call and System Call

| Function Call           | System Call                            |
| ----------------------- | -------------------------------------- |
| Executes in user space  | Executes in kernel space               |
| Faster                  | Slower due to mode switching           |
| No hardware access      | Can access hardware through the kernel |
| Calls program functions | Requests OS services                   |

## 6. Complete System Call Flow

![Complete System Call Flow]({{ '/assets/images/Complete-System-Call-Flow.png' | relative_url }})
