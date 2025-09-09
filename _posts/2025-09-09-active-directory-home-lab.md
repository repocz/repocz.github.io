---
layout: post
title: "Active Directory Home Lab"
description: "A hands-on exploration of Active Directory, from basic concepts to logical and physical structures."
date: 2025-09-09
categories: projects
permalink: /projects/active-directory-home-lab
author: "Mauricio"
---

# Active Directory Home Lab: Understanding the Basics

**Project Overview:**  
In this project, I explored the fundamentals of **Active Directory (AD)**, a core identity management platform used in Windows environments. My goal was to understand both the **logical and physical structures** of AD, how to manage users and groups, and how replication and permissions work in real-world scenarios.

---

## Planning & Context
Before diving in, I outlined key questions:  
- What is Active Directory and why is it essential?  
- How do logical structures (Organizational Units, users, and groups) work?  
- How does AD replication ensure high availability and performance?  
- How do modern cloud solutions like Azure AD relate to on-premises AD?

I set up a **Windows Server environment** to test these concepts practically.

---

## Understanding the Concepts
Active Directory is essentially a **database of objects**—users, groups, and devices—with **attributes** like first name, email, and permissions. Objects are organized into **Organizational Units (OUs)** for better management by location, department, or function.

From a **physical perspective**, AD relies on **domain controllers (DCs)** to store the database (`ntds.dit`). Multiple DCs allow for **replication**, preventing a single point of failure. Replication can occur **intra-site** (within a site) or **inter-site** (between geographically separated sites) depending on network bandwidth.

Modern environments may leverage **Azure Active Directory**, which shifts identity management to the cloud, providing a tenant-based structure and centralized management of users, devices, and groups.

---

## Implementation & Hands-On Work
1. **Server Setup:**  
   Installed **Windows Server 2016**, configured roles including **Active Directory Domain Services (AD DS)** and **DNS**.

2. **Logical AD Management:**  
   - Created **Organizational Units** such as `Operations`.  
   - Added **users** like `Chandler Roah` and `John Hall` with proper username conventions (`surname.initial`).  
   - Created **groups** like `Ops Managers` and assigned users to these groups for easier permissions management.  

3. **Exploring Attributes & Permissions:**  
   - Examined user properties (login times, password policies, profiles).  
   - Enabled account features like password expiration, session restrictions, and remote control for admin management.

4. **Physical AD Management:**  
   - Located the **AD database (`ntds.dit`)** and associated log files.  
   - Configured **sites and replication** for high availability.  
   - Set up multiple sites (e.g., London and Oslo) to simulate inter-site replication.  
   - Explored **Domains & Trusts** for potential forest and child domain relationships.

5. **Best Practices Learned:**  
   - Always have multiple DCs to avoid single points of failure.  
   - Organize users into OUs and groups to simplify permissions and policy management.  
   - Use recycle bin features to recover accidentally deleted AD objects.

---

## Lessons Learned
- Active Directory’s **core principles** have remained consistent since Windows 2000, making foundational knowledge relevant even with cloud integrations.  
- Understanding the difference between **logical and physical structures** is crucial for both management and disaster recovery.  
- Hands-on experimentation helps solidify concepts like replication, OU structuring, and user/group management.  
- Knowledge of Azure AD provides insight into hybrid environments that integrate on-premises and cloud identity management.

---

## Reflection
This lab gave me the opportunity to combine **theory and practice**, documenting not just how AD works, but also my thought process, troubleshooting steps, and decisions made along the way. It demonstrates my ability to **learn complex IT systems independently** and communicate the process effectively—perfect for showcasing in a portfolio.

