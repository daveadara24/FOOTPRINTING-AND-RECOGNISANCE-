# FOOTPRINTING-AND-RECOGNISANCE-

# Footprinting and Reconnaissance Using Kali Linux

![Platform](https://img.shields.io/badge/Platform-Kali%20Linux-blue)
![Category](https://img.shields.io/badge/Category-Cybersecurity-red)
![Status](https://img.shields.io/badge/Status-In%20Progress-orange)

## Project Overview

This repository documents practical cybersecurity exercises focused on Footprinting, Reconnaissance, Information Gathering, and Network Scanning using Kali Linux.

The project demonstrates the application of multiple reconnaissance tools to gather publicly available information about a target domain and examine its associated web technologies, DNS infrastructure, and network exposure.

The exercises are documented with command-line instructions, screenshots, observations, and technical analysis.

## Objectives

- Understand the principles of footprinting and reconnaissance.
- Gather domain registration information.
- Identify web technologies and server information.
- Perform DNS resolution and enumeration.
- Inspect HTTP response headers.
- Identify possible Web Application Firewall technologies.
- Gather publicly accessible information using theHarvester.
- Perform network scanning using Zenmap.
- Document and analyze reconnaissance findings.

## Lab Environment

| Component | Details |
|---|---|
| Operating System | Kali Linux |
| Target Domain | networkwalks.com |
| Assessment Type | Footprinting and Reconnaissance |
| Documentation | Markdown |
| Repository | GitHub |

## Tools Used

| Tool | Purpose |
|---|---|
| WHOIS | Domain registration lookup |
| WhatWeb | Web technology fingerprinting |
| Nslookup | DNS resolution |
| cURL | HTTP response header inspection |
| WAFW00F | Web Application Firewall detection |
| DNSRecon | DNS enumeration |
| theHarvester | Open-source intelligence gathering |
| Zenmap | Network scanning and visualization |

## Practical Exercises

### 1. Footprinting and Reconnaissance

The first exercise focuses on gathering information about networkwalks.com using the following tools:

1. WHOIS
2. WhatWeb
3. Nslookup
4. cURL
5. WAFW00F
6. DNSRecon

### 2. Footprinting and Reconnaissance with theHarvester

This exercise explores publicly available information associated with a target using theHarvester.

### 3. Network Scanning with Zenmap

This exercise focuses on network discovery and the identification of hosts, open ports, and services within the authorized assessment scope.

## Repository Structure

```text
footprinting-and-reconnaissance/
├── README.md
├── report/
│   └── reconnaissance-report.md
├── tools/
│   ├── whois.md
│   ├── whatweb.md
│   ├── nslookup.md
│   ├── curl.md
│   ├── wafw00f.md
│   └── dnsrecon.md
└── screenshots/
```

## Documentation and Evidence

Each practical exercise includes:

- Objective of the task
- Tool description
- Commands executed
- Screenshots of execution
- Observations and findings
- Technical analysis

See the [Detailed Reconnaissance Report](report/reconnaissance-report.md).

## Disclaimer

This repository is intended for educational and authorized cybersecurity testing purposes only.

All reconnaissance and scanning activities must be conducted within an approved scope. The documentation does not imply that vulnerabilities exist simply because information was discovered.

## Project Status

Currently in progress. Additional practical exercises, screenshots, findings, and analysis will be added as the project develops.
