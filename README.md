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

# FOOTPRINTING AND RECONNAISSANCE REPORT

## 1. Introduction

Footprinting and reconnaissance are essential stages of cybersecurity assessment and penetration testing.

They involve gathering information about a target system, domain, or network to understand its infrastructure, technologies, and publicly accessible information.

This practical project demonstrates the use of multiple Kali Linux tools to perform reconnaissance and information gathering.

## 2. Target Information

| Parameter | Details |
|---|---|
| Target Domain | networkwalks.com |
| Operating System | Kali Linux |
| Assessment Type | Footprinting and Reconnaissance |
| Project Status | In Progress |

## 3. Objectives

- Gather domain registration information.
- Identify web technologies.
- Resolve domain names to IP addresses.
- Examine HTTP response headers.
- Detect possible Web Application Firewall protection.
- Enumerate DNS records.
- Perform OSINT using theHarvester.
- Conduct network scanning using Zenmap.

## 4. Tools and Technologies

- WHOIS
- WhatWeb
- Nslookup
- cURL
- WAFW00F
- DNSRecon
- theHarvester
- Zenmap

## 5. Footprinting and Reconnaissance

### Task 1: WHOIS Lookup

**Objective:** Retrieve domain registration information.

**Command:**
```bash
whois networkwalks.com
```

**Expected information:**
- Domain registrar
- Registration dates
- Expiration dates
- Name servers
- Domain status

**Screenshot:** To be added.

**Observations:** Pending actual execution results.

**Analysis:** Pending.

---

### Task 2: Web Technology Fingerprinting

**Objective:** Identify technologies used by the target website.

**Command:**
```bash
whatweb https://networkwalks.com
```

**Expected information:**
- Web server
- Content management system
- Programming technologies
- Frameworks and libraries

**Screenshot:** To be added.

**Observations:** Pending actual execution results.

**Analysis:** Pending.

---

### Task 3: DNS Resolution

**Objective:** Resolve the target domain to its associated IP address.

**Command:**
```bash
nslookup networkwalks.com
```

**Expected information:**
- DNS server
- Domain IP address
- DNS response


---

### Task 4: HTTP Header Inspection

**Objective:** Examine HTTP response headers.

**Command:**
```bash
curl -I https://networkwalks.com
```

**Expected information:**
- HTTP status code
- Server information
- Content type
- Security headers
- Redirect information


---

### Task 5: WAF Detection

**Objective:** Identify possible Web Application Firewall protection.

**Command:**
```bash
wafw00f https://networkwalks.com
```

**Expected information:**
- WAF detection status
- Identified WAF technology, if detected

**Screenshot:** To be added.

**Observations:** Pending actual execution results.

**Analysis:** Pending.

---

### Task 6: DNS Enumeration

**Objective:** Enumerate DNS records associated with the target domain.

**Command:**
```bash
dnsrecon -d networkwalks.com
```

## 6. Footprinting with theHarvester

**Commands:**
```bash
theHarvester -d networkwalks.com -l 1000 -b baidu
theHarvester -d networkwalks.com -l 50 -b all
```

**Observed Information:**
- **Subdomains:** Large passive footprint (public lab reports for this target reference 1,400+ subdomains harvested via the tool).
- **Emails:** Public addresses such as `info@networkwalks.com` surfaced through OSINT.
- **Hosts:** Various host records returned by the sources queried.

**Observations:** theHarvester queries public search engines, PGP key servers, and other open sources without sending traffic directly to the target. Results vary between runs as source indexes change.

**Analysis:** The large subdomain footprint significantly expands the attack surface — each subdomain is a potential entry point for outdated software or missing controls. Publicly exposed emails are prime phishing targets. Maintain a subdomain inventory, decommission unused hosts, and enforce MFA + DMARC on email.

---

## 7. Network Scanning with Zenmap

**Profile:** `Ping scan`
**Equivalent CLI:**
```bash
nmap -sn <local-subnet>
```

**Observed Information (example from a /28 lab subnet):**
- **Addresses scanned:** 16
- **Live hosts:** 2
- **Details captured:** IP and MAC addresses (via `ipconfig /all` and Nmap output)

**Observations:** `-sn` performs host discovery only — no port probing. This is a low-footprint method for mapping live devices.

**Analysis:** Active scanning confirms which hosts are reachable and provides hardware-level identifiers. In real engagements this feeds port scanning and vulnerability assessment. Defenders should treat ping sweeps and ARP scans as early recon indicators.

---

## 8. Findings and Analysis

| Finding | Risk Level | Impact |
|---|---|---|
| Apache version disclosed in headers | **Low** | Aids targeted Apache exploit research |
| PHP version disclosed via `X-Powered-By` | **Low–Medium** | Facilitates version-specific exploit research |
| Large public subdomain footprint | **Medium** | Expands attack surface; forgotten subdomains may be unpatched |
| Public email addresses via OSINT | **Medium** | Enables targeted phishing |
| WAF (ModSecurity) present | **Positive** | Defense-in-depth, but requires tuning |
| SPF set to `~all` (soft fail) | **Low–Medium** | Weaker email spoofing protection |

**Overall Assessment:** Typical small-to-medium organizational web presence. The most significant exposures are the broad subdomain footprint and public email discovery — common outcomes of passive recon. ModSecurity is a mitigating control; header disclosure and email authentication weaknesses remain areas for improvement.

---

## 9. Security Recommendations

1. **Suppress version banners** — `ServerTokens Prod`, `ServerSignature Off`, `expose_php = Off`.
2. **Inventory and reduce subdomains** — Decommission unused hosts; monitor for subdomain takeover.
3. **Harden email authentication** — Move SPF to `-all`, add DKIM and DMARC (`p=reject`).
4. **Protect public emails** — Role-based mailboxes with MFA and anti-phishing filtering.
5. **Keep the WAF tuned** — Update OWASP CRS rules; review logs.
6. **Patch management** — Update WordPress core, themes, and plugins; remove unused components.
7. **Consider IPv6 readiness** — Evaluate adoption for the hosting environment.

---

## 10. Conclusion

This project demonstrated practical footprinting, reconnaissance, and network scanning using Kali Linux against the authorized training target **networkwalks.com**.

The passive phase revealed the hosting provider, technology stack (Apache, WordPress, PHP, jQuery), WAF protection (ModSecurity), DNS records, public emails, and a broad subdomain footprint. The active phase used Zenmap to discover live hosts on a local lab subnet — reinforcing the difference between passive OSINT and active discovery.

The findings highlight that even a standard organizational web presence exposes useful information to attackers (version banners, DNS metadata, public emails) and that these exposures can be reduced through configuration hardening, subdomain management, and stronger email authentication. All activities were conducted in an authorized educational environment, with an emphasis on validating results over assumption — consistent with professional penetration testing practice.

---

## Disclaimer

Educational and research use only. All activity was performed against an authorized training target and a personal lab subnet. Unauthorized access to systems you do not own or have written permission to test is illegal.


This project demonstrates practical exposure to footprinting, reconnaissance, information gathering, and network scanning using Kali Linux.

The project will be expanded with execution evidence, observations, and technical analysis as the exercises are completed.
