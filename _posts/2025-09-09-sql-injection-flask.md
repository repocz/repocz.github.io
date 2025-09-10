---
layout: post
title: "SQL Injection Protection Flask Web Application"
description: "Building a secure web application in Flask by implementing defenses against SQL Injection attacks."
date: 2025-09-10
categories: projects
permalink: /projects/sql-injection-flask
---

## Planning and Overview
For this project, my classmate Truett Davis and I set out to design a Flask web application with a primary focus on **security against SQL Injection attacks**. The application included core features such as login, search, and user profile pages. From the start, the goal wasn’t just to make the app functional, but to make it **resilient to common web vulnerabilities** that often go overlooked in development.

Before diving into implementation, we researched SQL Injection attacks and how attackers take advantage of poorly handled user input. That understanding helped us plan out how to structure the app and what safeguards we needed to build in from the beginning.

---

## Understanding the Concepts
SQL Injection occurs when user input is directly passed into a SQL query without validation. Attackers can exploit this to **manipulate database queries**—from bypassing logins to retrieving sensitive data.

![SQL Screenshot](/assets/images/projects/sql.png)

To prevent that, we focused on three main concepts:  

- **Parameterized Queries** – Ensuring user inputs are treated strictly as data and never as executable SQL code.  
- **Input Validation & Sanitization** – Checking all incoming data to make sure it matches expected formats, while cleaning potentially harmful characters.  
- **Error Handling** – Avoiding detailed error outputs that might leak sensitive information about the database or app logic.  

These practices built the foundation of our secure web application.

![SQL Screenshot](/assets/images/projects/sql2.png)

---

## Implementation
We used **Flask** as the framework, with different routes (login, search, and profile) carefully updated to prevent SQL injection:

- **Login Route** – The login logic used parameterized queries, making it impossible for attackers to inject SQL through the username or password fields.  
- **Search Route** – Search functionality safely handled user queries without exposing the backend to malicious inputs.  
- **Profile Route** – Profiles were retrieved securely using validated IDs, preventing direct query manipulation.  

On the front end, we also designed **HTML forms** (login, search, and profile pages) that properly handled input and worked hand-in-hand with our back-end validation.

![SQL Screenshot](/assets/images/projects/sql3.png)

---

## Skills Learned
Working on this project helped me strengthen several key skills:  

- **Web Security Awareness** – Gained a deeper understanding of how common vulnerabilities like SQL injection actually work.  
- **Secure Coding Practices** – Learned how to integrate parameterized queries, input validation, and error handling into real applications.  
- **Flask Development** – Built and secured routes, templates, and forms in Flask while ensuring the app was user-friendly.  
- **Team Collaboration** – Planned, implemented, and tested solutions with my classmate, sharing knowledge and responsibilities.  

---

## Conclusion
By applying secure coding techniques, we built a Flask web application that is **resistant to SQL Injection attacks**. This project reinforced how small coding mistakes can lead to major vulnerabilities, and how best practices like parameterized queries and validation can protect both developers and users.  

This hands-on experience not only improved my technical skills but also strengthened my approach to security-first development.
