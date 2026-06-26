# CIA Triad — SOC and Cloud Security Example

## Concept

The CIA Triad is a core cybersecurity model made of:

* Confidentiality
* Integrity
* Availability

SOC analysts use the CIA Triad to understand the impact of security incidents and decide how serious an alert or event may be.

## 1. Confidentiality

Confidentiality means only authorised people, systems, or services should access sensitive data.

### Daily-Life Example

A personal bank account should only be visible to the account holder after proper login.

### SOC Example

A SOC analyst may investigate whether an unauthorised user accessed sensitive files, customer records, internal documents, or cloud storage.

### Cloud Security Example

An AWS S3 bucket should not be publicly accessible unless there is a valid business reason. If private files are exposed publicly, confidentiality is broken.

## 2. Integrity

Integrity means data should remain accurate, complete, and unchanged unless modified by an authorised user or process.

### Daily-Life Example

If someone changes the amount on an invoice without permission, the integrity of that document is broken.

### SOC Example

A SOC analyst may investigate whether malware modified system files, whether an attacker changed logs, or whether suspicious activity altered application data.

### Cloud Security Example

AWS CloudTrail logs should be protected so attackers cannot delete or modify evidence of their activity.

## 3. Availability

Availability means systems, services, and data should be accessible when needed.

### Daily-Life Example

A banking app should be available when customers need to transfer money.

### SOC Example

A SOC analyst may investigate denial-of-service activity, ransomware, service outages, or unusual traffic spikes affecting business operations.

### Cloud Security Example

A cloud application should use monitoring, backups, redundancy, and alerting to stay available during failures or attacks.

## Mini Incident Scenario

A company discovers that a cloud storage bucket was accidentally made public.

## Security Impact

* Confidentiality is affected because unauthorised people may access private data.
* Integrity may be affected if attackers can modify files.
* Availability may be affected if attackers delete, disrupt, or abuse access to files.

## SOC Analyst Response

1. Confirm whether the storage bucket is publicly accessible.
2. Identify what data may have been exposed.
3. Review access logs for suspicious activity.
4. Remove public access immediately.
5. Rotate exposed credentials if needed.
6. Document the incident clearly.
7. Recommend stronger access control, monitoring, and alerting.
8. Review whether similar misconfigurations exist elsewhere.

## What I Learned

The CIA Triad helps SOC analysts classify the impact of an incident. It gives a simple structure for understanding whether an event affects data privacy, data accuracy, or business availability.