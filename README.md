# OneDrive Application Integrity Automation Optimization

## Ownership Notice

The original automation code referenced in this document was developed during my time at ThreatLocker and remains the intellectual property of ThreatLocker.

I do not possess or distribute the original source code. This document only describes my technical contributions, problem-solving approach, and the engineering concepts involved.

---

# Overview

During my time at ThreatLocker, I contributed to an internal Python automation workflow designed to improve application integrity verification for Microsoft OneDrive releases.

The purpose of the workflow was to collect trusted application hashes that could be used to validate file authenticity and support endpoint security controls.

The automation pipeline supported the process of:

- Identifying official OneDrive releases
- Retrieving release files
- Downloading binaries into a controlled environment
- Generating file hashes
- Validating application integrity
- Adding trusted hash information into client security profiles

---

# Problem

The existing process required evaluating multiple Microsoft OneDrive versions and subversions to build a trusted hash database.

A challenge was ensuring the workflow was efficient while maintaining complete coverage of legitimate releases.

Searching every possible historical subversion introduced unnecessary processing overhead.

---

# My Contribution

My primary contribution was analyzing the version discovery process and improving the logic used to identify which OneDrive versions required processing.

I identified that Microsoft OneDrive version releases followed a sequential progression and did not require repeatedly searching previously processed versions or assuming releases would appear out of order.

Based on this observation, I contributed logic that allowed the workflow to begin from the most recently captured version and continue forward.

This reduced unnecessary searching and improved processing efficiency while maintaining the intended security objective.

---

# Technical Workflow
Microsoft Release Repository
|
|
Version Discovery
|
|
Download Official Files
|
|
Controlled Sandbox Execution
|
|
Generate File Hashes
(MD5 / SHA256)
|
|
Hash Database
|
|
Endpoint Integrity Validation

---

---

# Security Purpose

The goal of this workflow was to support application integrity verification.

By maintaining trusted hashes of legitimate releases, endpoint security controls could compare files against known-good values and help prevent unauthorized or modified binaries from executing.

Security concepts involved:

- File integrity verification
- Application allowlisting
- Software supply chain security
- Endpoint protection
- Hash-based validation

---

# Technical Lessons Learned

This project reinforced the importance of understanding system behavior before optimizing automation.

Rather than only improving code execution speed, I analyzed the underlying release process and identified an opportunity to remove unnecessary processing while preserving security requirements.

This experience strengthened my ability to evaluate workflows, identify inefficiencies, and contribute improvements within a collaborative engineering environment.

# Development Process 

AI tools were used as a development assistant during this project to accelerate troubleshooting, explore implementation approaches, and assist with scripting.

The system architecture, security decisions, testing, troubleshooting, and final implementation choices were performed and validated by me.
