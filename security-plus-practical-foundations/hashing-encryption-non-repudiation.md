# Hashing, Encryption, and Non-Repudiation

## Topic Summary

Hashing, encryption, and non-repudiation are core Security+ ideas that support confidentiality, integrity, and trust. They are related, but they solve different problems. Hashing helps detect changes, encryption protects data from unauthorised viewing, and non-repudiation helps prove that a specific action really happened.

## Key Definitions

* Hashing: converting data into a fixed-length value used to check integrity
* Hash function: an algorithm such as SHA-256 that produces a digest from input data
* Encryption: converting readable data into unreadable ciphertext so only authorised parties can recover it
* Symmetric encryption: the same key is used to encrypt and decrypt data
* Asymmetric encryption: a public key and private key pair are used for encryption or signatures
* Digital signature: a cryptographic method used to verify sender authenticity and message integrity
* Non-repudiation: evidence that helps prevent someone from denying they performed an action

## Daily-Life Example

Sealing a letter inside an envelope is like encryption because it hides the content. Signing the outside of the letter is like non-repudiation because it helps show who sent it. Checking whether the letter was changed in transit is like hashing and integrity validation.

## SOC Analyst Use Case

A SOC analyst may compare the known-good hash of a system file against the current file hash after a malware alert. If the hash changed unexpectedly, it may show tampering. The analyst may also review whether a signed email or document was altered after delivery.

## Cloud Security Example

In cloud platforms, encryption protects data at rest and in transit. For example, an S3 bucket can use server-side encryption, and HTTPS protects web traffic. Hashing can support integrity checks for uploaded files, while signed API requests and certificates help validate trusted communication.

## Mini Incident Scenario

A finance team receives an email attachment that appears to be a legitimate invoice, but the file hash does not match the approved version stored internally. The sender claims the file is original.

## Practical Task or Observation Activity

1. Pick a sample file and calculate its hash with a common algorithm such as SHA-256.
2. Change a single character in the file and calculate the hash again.
3. Observe how a very small change creates a very different hash output.
4. Write a short note explaining when hashing checks integrity and when encryption protects confidentiality.
5. Identify where digital signatures would provide stronger proof of origin.

## Exam Traps

* Hashing is not encryption because hashes are not meant to be reversed.
* Encryption protects confidentiality, but it does not automatically prove the sender identity.
* Integrity and non-repudiation are related but different. A file can be intact without proving who created it.
* MD5 and SHA-1 may appear in older systems, but they are weak compared with stronger modern hashing choices.

## What I Learned

Hashing, encryption, and non-repudiation each solve a different security problem. Understanding that difference helps me explain alerts more clearly, verify suspicious files, and understand why cloud services use multiple cryptographic controls together.