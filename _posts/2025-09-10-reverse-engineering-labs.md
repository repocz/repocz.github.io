---
layout: post
title: "Reverse Engineering & Debugging Labs"
description: "A collection of reverse engineering labs where I practiced debugging, bypassing protections, and recovering hidden flags."
date: 2025-09-10
categories: projects
permalink: /projects/reverse-engineering-labs
---

## Planning and Overview
This project was a series of reverse engineering labs focused on capturing hidden flags from binaries while overcoming different challenges like **anti-debugging, encoding, and restricted execution permissions**.  

Throughout the labs, I worked with tools such as **IDA, Ghidra, OllyDbg, Cutter, Binary Ninja, EDB, ltrace, and CyberChef**, along with common Linux utilities like `strings`, `chmod`, and command-line debugging.  

The overall objective was not just to recover flags, but to build confidence in analyzing executables, modifying assembly instructions, patching binaries, and recognizing how attackers and defenders approach software security.

---

## Understanding the Concepts
Each lab presented variations of real-world reverse engineering problems:  

- **Anti-Debugging Checks**: Many binaries included functions like `IsDebuggerPresent` or hardcoded checks for debuggers (`immunitydebugger`, `ollydbg.exe`), designed to stop traditional analysis tools.  
- **Breakpoints & Patching**: By identifying key instructions (`CMP`, `JNZ`, `MEMCMP`, etc.), I patched binaries or redirected execution flow to bypass anti-analysis logic.  
- **Flag Extraction**: Flags were often hidden in memory, registers, or encoded segments. Dumping memory, following registers, or adjusting offsets in functions allowed me to reveal them.  
- **Linux Executable Permissions**: Some binaries had restricted permissions. By using `chmod +x`, I could execute them, then apply tools like `strings` or `ltrace` to uncover flag values.  

![RE Screenshot](/assets/images/projects/re1.png) 

This reinforced how small protective mechanisms can complicate analysis, and how persistence with the right tools makes it possible to bypass them.

---

## Implementation
Over the course of the labs, I approached the problems systematically:

1. **Static Analysis with Ghidra/IDA**  
   - Located suspicious functions (`CreateToolhelp32Snapshot`, debugger checks, memcopy operations).  
   - Identified offsets and arguments related to flag handling.  

   ![RE Screenshot](/assets/images/projects/re4.png) 

2. **Dynamic Debugging with OllyDbg & EDB**  
   - Set breakpoints on critical functions (e.g., `0x401BE9`, `0x4009ED`).  
   - Patched instructions such as `XOR EAX, EAX` to zero out anti-debugging logic.  
   - Tracked flags as they appeared in registers (`RAX`, `ESI`, etc.) or in memory dumps.  

![RE Screenshot](/assets/images/projects/re2.png) 

3. **Command-Line & Scripting**  
   - Used `strings` and `floss` to quickly spot hints about hidden debugger detection and flag formatting.  
   - Ran `ltrace -s 40 ./binary` to capture full function calls and recover flags directly from arguments.  
   - Adjusted file permissions (`chmod +x`) to execute restricted binaries.  

4. **Alternate Tools**  
   - **Cutter & Binary Ninja** were used when certain functions were easier to visualize or patch in different disassemblers.  
   - **CyberChef** came in handy when encoded data needed quick decoding or formatting.  

---

## Skills Learned
This project gave me hands-on exposure to practical reverse engineering challenges. Key skills I developed include:  

- **Reverse Engineering Workflows** – Navigating disassemblers, identifying critical code paths, and correlating assembly instructions with program logic.  
- **Debugging & Patching** – Using OllyDbg, EDB, and Cutter to bypass anti-debugging and manipulate execution flow.  
- **Binary & Memory Analysis** – Locating flags in registers, stack frames, and memory dumps.  
- **Linux Command-Line Proficiency** – Applying `chmod`, `strings`, `ltrace`, and related tools to work with binaries.  
- **Problem-Solving Under Constraints** – Combining static and dynamic analysis methods to recover flags even when protections were in place.  

---

## Conclusion
By completing these labs, I strengthened my ability to analyze, patch, and debug executables under different conditions. From bypassing anti-debugging logic to uncovering hidden flags in memory, each exercise added to my reverse engineering toolkit.  

This project deepened my understanding of **how attackers use obfuscation to protect binaries**—and how defenders (or analysts) can systematically break through those defenses. More importantly, it taught me persistence, creativity, and how to combine multiple tools to achieve a successful outcome.
