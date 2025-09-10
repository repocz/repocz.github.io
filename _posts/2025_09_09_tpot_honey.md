---
layout: post
title: "T-Pot Honeypot Deployment and Cyber Analysis"
date: 2025-09-09
categories: projects
permalink: /projects/tpot-honeypot
---

# Honeypot Deployment and Cyber Analysis Using T-Pot

**Author:** Mauricio Spadoni  
**Course:** CYBR 4950 — University of North Georgia  
**Professor:** Yong Wei  
**Date:** May 6, 2025

## Abstract

This capstone project focuses on the deployment of a honeypot system using the T-Pot framework to detect and analyze real-world cyber threats. The study created a secure, isolated honeypot environment that captures attacker behavior and malicious activity. Technologies used include Docker, Elasticsearch, Kibana, and SpiderFoot for data collection, visualization, and intelligence gathering. The project emphasizes hands-on server setup, Linux command-line proficiency, and security operations.

## Introduction

As cyber threats increase in complexity and volume, honeypots provide proactive visibility into attacker tactics and behavior. T-Pot is an integrated, Docker-based platform that bundles multiple honeypot sensors and analytics tools. This project deployed a multi-sensor T-Pot honeypot to monitor common attack vectors (SSH, Telnet, HTTP) and analyze captured telemetry with the ELK stack and OSINT tools.

## Project Scope and Objectives

**Primary goals:**

1. Deploy a secure, isolated T-Pot environment on a cloud server.
2. Simulate and capture attack vectors such as brute-force logins and reconnaissance.
3. Analyze collected data using ELK (Elasticsearch, Logstash, Kibana) and SpiderFoot.
4. Document attacker behavior, identify threat patterns, and present actionable insights.

The honeypot was configured to emulate services frequently targeted by attackers: SSH (22), Telnet (23), and web services (80/443).

## Methodology

### Server Deployment and Setup

A virtual private server (DigitalOcean) was provisioned running Debian 11 with a minimum configuration of 4 CPU cores, 16 GB RAM, and 256 GB SSD. SSH access used key-based authentication and the server was hardened before deployment.

### T-Pot Framework Installation

T-Pot was installed using the official ISO and deployed under Docker. T-Pot’s integrated sensors (e.g., Cowrie, Dionaea, Honeytrap) and analytics tools were used as provided by the framework.

### Linux Command-Line Workflows

All configuration and troubleshooting were performed via the Linux command line: system updates, network configuration, user management, and log collection.

### Docker Orchestration

Because T-Pot uses containerized services, managing Docker and container interactions was a central part of the deployment. Logs and inter-container networking were examined to ensure correct data flow to Elasticsearch and Kibana.

### Network Isolation and Security Controls

Planning in VirtualBox allowed safe testing. In production, firewall rules and isolated VLANs prevented lateral movement while allowing the honeypot to attract and capture external traffic.

## Data Collection and Analysis

During the observation period, the honeypot recorded over **151,000** attack attempts. Cowrie (SSH/Telnet sensor) recorded **70,000+** hits and was the most-targeted sensor. Other active sensors included Honeytrap and Dionaea. Common attack types were brute-force SSH logins, unauthorized HTTP access, and attempts at malware propagation.

Kibana dashboards showed frequently used usernames such as `root`, `admin`, and `ubuntu`, and weak passwords including `123456` and `admin`. Attack source geolocation was diverse; the United States, China, and the Netherlands were among the top origin countries.

SpiderFoot was used to enrich attacker IPs and domains with OSINT (WHOIS, passive DNS, reputation data), helping identify potentially compromised infrastructure.

## Challenges and Solutions

- **Framework selection:** Initial testing revealed differences across honeypot solutions. T-Pot was selected for its integrated toolset and extensibility.
- **Network configuration:** Proper isolation required careful virtual network and firewall configuration.
- **Tool compatibility:** Integrating external tools (Splunk, Wireshark) into the environment presented dependency issues; native T-Pot tools were used when appropriate.

## Results and Key Findings

- SSH brute-force attempts were the highest-volume attack vector.
- Attackers commonly used default or weak credentials, indicating opportunistic, low-effort compromise attempts.
- Real-time dashboards enabled quick assessment of incident volume and geographic distribution.
- Combining ELK-based telemetry with SpiderFoot OSINT yielded richer context for threat intelligence.

## Conclusion

Deploying a T-Pot honeypot demonstrated the value of hands-on honeypot operations: it deepened skills in server administration, Docker, Linux command-line work, and threat analysis. The project produced actionable insights into common attacker behaviors and highlighted areas for improving detection and response.

## Future Work

Potential improvements:

- Integrate Splunk for advanced correlation and search features.
- Automate alerts and triage with TheHive and Cortex.
- Expand intelligence enrichment using Maltego and additional OSINT sources.
- Implement automated analysis pipelines for malware samples captured by honeypot sensors.

## References

- Spitzner, L. (2003). *Honeypots: Tracking Hackers*. Addison-Wesley.
- Deutsche Telekom Security GmbH. (2023). *T-Pot: The All-In-One Multi Honeypot Platform* — https://github.com/telekom-security/tpotce
- Elastic. (2023). *The Elastic Stack* — https://www.elastic.co/what-is/elk-stack
- SpiderFoot. (2023). *Automated OSINT Tool* — https://www.spiderfoot.net/
- Docker Inc. (2023). *What is Docker?* — https://www.docker.com/resources/what-container/

---

*This page was generated from the capstone report.*

