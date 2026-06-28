# Hashing, Encryption, and Non-Repudiation

## Topic Summary

Hashing, encryption, and non-repudiation are core Security+ concepts that support confidentiality, integrity, authenticity, and trust. They are related, but they solve different security problems.

* **Hashing** helps verify whether data has changed.
* **Encryption** protects data from unauthorised viewing.
* **Digital signatures** help prove authenticity and integrity.
* **Non-repudiation** provides evidence that a user, system, or sender performed an action and cannot reasonably deny it later.

For SOC analysts, these concepts appear during malware investigation, file integrity checks, phishing analysis, certificate review, signed script analysis, and cloud security monitoring.

## Key Definitions

* **Hashing:** converting data into a fixed-length value called a hash or digest. Hashing is one-way and is mainly used for integrity checking.
* **Hash function:** an algorithm such as SHA-256 that produces a digest from input data.
* **Encryption:** converting readable plaintext into unreadable ciphertext so only authorised parties with the correct key can recover it.
* **Symmetric encryption:** the same key is used to encrypt and decrypt data. It is usually faster and used for bulk data encryption.
* **Asymmetric encryption:** a public/private key pair is used. It supports secure key exchange, digital signatures, and identity validation.
* **Digital signature:** a cryptographic method used to verify sender authenticity and message integrity.
* **Non-repudiation:** evidence that helps prevent someone from denying they performed an action.
* **Salting:** adding random data before hashing a password to make precomputed attacks such as rainbow tables less useful.
* **Key stretching:** making password hashing slower and more resistant to brute-force attacks using algorithms such as PBKDF2, bcrypt, or scrypt.

## Daily-Life Example

Sealing a letter inside an envelope is like encryption because it hides the content. Signing the letter is like a digital signature because it helps show who sent it. Checking whether the letter was changed in transit is like hashing and integrity validation.

## SOC Analyst Use Case

A SOC analyst may compare the known-good hash of a system file against the current file hash after a malware alert. If the hash changed unexpectedly, it may show tampering. File hashes can also be searched in threat intelligence tools such as VirusTotal to check whether a file is known to be malicious.

SOC analysts may use hashing and signature concepts when investigating:

* suspicious executable files
* malware alerts
* modified system files
* signed or unsigned PowerShell scripts
* phishing attachments
* suspicious software downloads
* file integrity monitoring alerts

## Cloud Security Example

In cloud platforms, encryption protects data at rest and in transit. For example, AWS S3 can use server-side encryption, and HTTPS/TLS protects web traffic. Hashing can support file integrity checks, while signed API requests, certificates, and key management services help validate trusted communication.

Cloud examples include:

* S3 bucket encryption for data at rest
* HTTPS/TLS for data in transit
* AWS KMS for key management
* signed API requests
* CloudTrail log integrity validation
* checking whether uploaded files were modified

## Mini Incident Scenario

A finance team receives an email attachment that appears to be a legitimate invoice, but the file hash does not match the approved version stored internally. The sender claims the file is original.

A SOC analyst should treat this as suspicious because the hash mismatch indicates the file content changed. The analyst should investigate whether the file was modified, replaced, or weaponised.

## Practical Task: SHA-256 File Hash Test

I created a test file in PowerShell, generated a SHA-256 hash, changed the file content, and generated the hash again.

### Commands Used

```powershell
cd $env:USERPROFILE\Documents
mkdir security-lab
cd security-lab

"hello security" | Out-File test.txt
Get-FileHash .\test.txt -Algorithm SHA256

"hello security changed" | Out-File test.txt
Get-FileHash .\test.txt -Algorithm SHA256
```

### Results

First file content:

```text
hello security
```

First SHA-256 hash:

```text
61FDCF2D203CCAF871594988BF0DD61858FA5C965CAD76758149466DDDC4357F
```

Modified file content:

```text
hello security changed
```

Second SHA-256 hash:

```text
6EFCCDC49F372DAE92F1CC59EE31C280A93FFA51A3709B897E68913009BBF7B
```

## Practical Observation

The hash changed completely after the file content changed. This shows the avalanche effect: even a small change to input data produces a very different hash output.

This proves that hashing is useful for detecting file modification. It does not hide the file content and it cannot be reversed back into the original text.

## Exam Traps

* Hashing is not encryption because hashes are not meant to be reversed.
* Encryption protects confidentiality, while hashing mainly supports integrity.
* A digital signature provides authenticity and integrity, and can support non-repudiation.
* A hash alone does not prove who created a file.
* MD5 and SHA-1 may appear in older systems, but they are weak compared with stronger modern choices such as SHA-256.
* Salting protects password hashes from rainbow table attacks.
* Key stretching slows down password-cracking attempts.

## Interview Explanation

Hashing creates a fixed-length fingerprint of data. If the file changes, the hash changes. A SOC analyst can use file hashes to verify file integrity, compare suspicious files with known-good files, and search threat intelligence sources for known malicious hashes. Hashing is different from encryption because encryption is reversible with a key, while hashing is one-way.

## What I Learned

Hashing, encryption, and non-repudiation each solve a different security problem. The PowerShell mini-lab helped me see that hashing is mainly used for integrity checking. This is directly useful in SOC work because analysts often need to verify whether a file has been modified, whether a suspicious attachment is known malware, or whether logs and evidence remain trustworthy.
