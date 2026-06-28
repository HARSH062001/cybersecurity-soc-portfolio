# Security+ Domain 1 — Mastery Summary

## Status

Security+ Domain 1: General Security Concepts — **completed first mastery pass**.

This means I have completed the first serious learning cycle for Domain 1, including video-based study, NotebookLM revision, quiz validation, practical mini-labs, and GitHub documentation.

This does not mean I am finished forever. Domain 1 should still be revised weekly while I continue through later Security+ domains.

## Study Sources Used

* Professor Messer Security+ SY0-701 Domain 1 videos
* NotebookLM explanations and podcasts based on uploaded video sources
* Security+ style quizzes generated from the study material
* Practical PowerShell hashing mini-lab
* Browser certificate inspection activity

## Quiz Checkpoints

| Quiz | Score | Result |
|---|---:|---|
| First Domain 1 quiz | 14/15 = 93% | Passed |
| Mixed Domain 1 quiz | 22/25 = 88% | Passed |
| Weak-topic quiz | 13/15 = 87% | Passed |

## Topics Covered

* CIA triad
* AAA framework: authentication, authorization, and accounting
* Security control categories and types
* Zero Trust architecture
* Public Key Infrastructure (PKI)
* X.509 certificates
* Digital certificates and certificate revocation
* Cryptography and hashing
* Symmetric and asymmetric encryption
* Digital signatures and non-repudiation
* Salting, key stretching, and rainbow table protection
* Physical security controls
* Deception and obfuscation techniques
* Gap analysis
* Change management
* Business continuity and disaster recovery basics

## Practical Evidence Completed

### 1. CIA Triad Scenario

I documented how confidentiality, integrity, and availability apply to a public cloud storage bucket exposure scenario.

### 2. AAA and Zero Trust Scenario

I documented how authentication, authorization, accounting, MFA, least privilege, and Zero Trust apply to suspicious login investigation and cloud IAM access review.

### 3. Hashing Mini-Lab

I created a file in PowerShell, generated a SHA-256 hash, changed the file content, and generated the hash again.

First SHA-256 hash:

```text
61FDCF2D203CCAF871594988BF0DD61858FA5C965CAD76758149466DDDC4357F
```

Second SHA-256 hash after modifying file content:

```text
6EFCCDC49F372DAE92F1CC59EE31C280A93FFA51A3709B897E68913009BBF7B
```

Lesson learned: a small file change produced a completely different hash. This shows why hashing is useful for file integrity checking in SOC investigations.

### 4. Security Controls Mapping

I documented preventive, detective, corrective, deterrent, compensating, administrative, technical, and physical controls using SOC and cloud examples.

### 5. Certificate Inspection

I inspected the TLS certificate for `github.com`.

Observed details:

| Field | Value |
|---|---|
| Issued to | `github.com` |
| Issued by | `Sectigo Public Server Authentication CA DV E36` |
| Organisation | `Sectigo Limited` |
| Valid from | Tuesday, May 5, 2026 at 10:00 AM |
| Valid until | Monday, August 3, 2026 at 9:59 AM |
| Certificate chain | Sectigo Public Server Authentication Root E46 → Sectigo Public Server Authentication CA DV E36 → github.com |

Lesson learned: certificates help browsers validate server identity and establish encrypted HTTPS communication, but a valid certificate does not automatically mean a website is safe.

## SOC Analyst Connections

Domain 1 concepts connect directly to SOC work:

* CIA triad helps classify incident impact.
* AAA helps investigate suspicious logins and account activity.
* Security controls help identify what prevented, detected, or failed during an incident.
* Hashing helps verify file integrity and investigate suspicious files.
* PKI knowledge helps investigate certificate warnings, phishing sites, and TLS issues.
* Zero Trust supports least privilege, continuous verification, and reduced blast radius.

## Cloud Security Connections

Domain 1 also connects to cloud security:

* IAM policies support authorization and least privilege.
* CloudTrail supports accounting and investigation.
* S3 encryption supports confidentiality.
* CloudTrail log integrity supports integrity.
* Certificate management supports HTTPS trust and availability.
* GuardDuty and SIEM alerts support detective controls.
* MFA and conditional access reduce account takeover risk.

## Weak Topics to Continue Revising

* DES vs AES
* Diffie-Hellman key exchange
* Symmetric vs asymmetric encryption speed and overhead
* HSM and cryptographic accelerators
* Network Access Control
* MFA factor categories
* Disaster recovery vs business continuity
* Blockchain as a distributed ledger
* Change management and backout procedures
* SAN certificates vs wildcard certificates

## Interview Explanation

Security+ Domain 1 gave me the foundation to explain how organisations protect data, verify identity, manage access, build trust, and reduce risk. I connected the theory to SOC examples such as suspicious logins, file integrity checks, certificate warnings, and cloud access review. This helps me think more like a junior SOC analyst instead of only memorising exam definitions.

## Next Steps

* Continue weekly revision of weak topics.
* Start Security+ Domain 2.
* Build a phishing email investigation project.
* Build a failed-login or brute-force detection lab.
* Continue adding screenshots and practical evidence to this portfolio.
