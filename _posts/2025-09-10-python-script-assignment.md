---
layout: post
title: "Python Scripting Assignment"
description: "This assignment involved creating several Python scripts and functions that demonstrate core programming concepts such as file handling, hashing, randomization, set operations, and brute-force techniques. The tasks were designed to strengthen scripting skills while applying them to practical scenarios."
date: 2025-09-10
categories: projects
permalink: /projects/python-script-assignment
---

## Overview
This assignment involved creating several Python scripts and functions that demonstrate core programming concepts such as file handling, hashing, randomization, set operations, and brute-force techniques. The tasks were designed to strengthen scripting skills while applying them to practical scenarios.

---

## Tasks

### 1. Generate Random Student IDs
**Function:** `Random_studentID()`  
- Randomly generates 100 possible UNG student IDs.  
- Each ID must be 9 digits and begin with `900`.  
- Outputs all IDs into a file named `randomID.txt`.

![Python Screenshot](/assets/images/projects/script.png) 

---

### 2. Convert Unix/Epoch Timestamps
**Function:** `convert_utime()`  
- Reads Unix timestamps from `unixttimestamp.txt`.  
- Converts each timestamp into a human-readable date/time.  
- Prints the results to the console.  

![Python Screenshot](/assets/images/projects/script2.png)  

---

### 3. Register Users for a Conference
**Function:** `register_user()`  
- Uses a set to track registered users and avoid duplicates.  
- Checks usernames against those stored in `conference.txt`.  
- Adds new users if they are not already registered.  

![Python Screenshot](/assets/images/projects/script3.png) 

---

### 4. Generate SHA256 Hashes for 7-Digit PINs
**Function:** `generate_sha256()`  
- Generates all possible 7-digit PINs.  
- Computes the corresponding SHA256 hash for each PIN.  
- Saves results in `rainbow.csv` (PIN, hash).  

![Python Screenshot](/assets/images/projects/script5.png) 

---

### 5. Compress Dictionary Words into a Password-Protected Zip
**Script:**  
- Reads dictionary words from `wordlist.txt`.  
- Saves them into a file.  
- Compresses the file into a **password-protected zip archive**.  

![Python Screenshot](/assets/images/projects/script6.png)  

---

### 6. Brute Force the Password-Protected Zip
**Script:**  
- Performs brute force to extract the zip created in Task 5.  
- Tests words from `wordlist.txt` as possible passwords.  
- Successfully opens the zip file once the correct password is found.  

![Python Screenshot](/assets/images/projects/script8.png)  

---

## Reflection
This assignment provided practical experience with:  
- File handling and input/output in Python.  
- Working with timestamps and conversions.  
- Using sets to avoid duplicates.  
- Cryptographic hashing (SHA256) and rainbow table creation.  
- Compressing and securing files with passwords.  
- Implementing brute force techniques on protected files.  

These exercises reinforced my understanding of Python scripting in security and system utility contexts.

---
