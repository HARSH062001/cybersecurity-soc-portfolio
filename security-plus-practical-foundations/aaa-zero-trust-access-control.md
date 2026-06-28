# AAA and Zero Trust Access Control

## Topic Summary

AAA stands for Authentication, Authorization, and Accounting. These ideas help security teams confirm who a user is, what they are allowed to do, and what actions they performed. Zero Trust builds on this by assuming no user, device, or network connection should be trusted automatically.

For Security+ and real-world SOC work, AAA and Zero Trust are important because they connect identity, access control, monitoring, and least privilege into one practical security model.

## Key Definitions

* Authentication: proving that a user, device, or service is really who it claims to be
* Authorization: deciding what an authenticated user or system is allowed to access or change
* Accounting: logging and tracking user actions for auditing and investigations
* Least privilege: giving only the minimum access needed to complete a task
* Zero Trust: a security model that continuously verifies identity, device posture, and access context instead of trusting by default
* Multifactor authentication (MFA): using two or more factors such as a password, phone prompt, or hardware token

## Daily-Life Example

A person enters a secure office building by scanning an ID card and then entering a PIN. The badge confirms identity, the building system decides which doors they can open, and the access system logs the time and location of entry.

## SOC Analyst Use Case

A SOC analyst may investigate repeated failed MFA prompts followed by a successful login from an unusual location. Authentication logs help show whether a user was targeted for credential theft, authorization settings help confirm what the attacker could access, and accounting logs help reveal what happened after login.

## Cloud Security Example

In AWS, IAM policies control which users and roles can access services such as S3 or EC2. A Zero Trust approach would require strong authentication, short-lived access, role-based permissions, logging through CloudTrail, and review of unusual access patterns instead of assuming internal users are safe.

## Mini Incident Scenario

An employee account is successfully logged into from a foreign IP address late at night. Minutes later, the account accesses cloud storage it does not normally use.

## Practical Task or Observation Activity

1. Review a sample login event and identify the authentication method used.
2. Ask what permissions the account should normally have.
3. Check whether logging exists to show what files, systems, or cloud services were accessed.
4. Compare the event against least privilege and normal user behaviour.
5. Write a short note on whether the activity looks legitimate, suspicious, or clearly malicious.

## Exam Traps

* Authentication and authorization are not the same thing. Logging in is authentication, while permission to open a file is authorization.
* Accounting is often overlooked, but it matters for investigations and audit trails.
* Zero Trust does not mean trusting nothing forever. It means verifying continuously and limiting access based on context.
* MFA improves authentication, but it does not replace authorization or logging.

## What I Learned

AAA gives a simple way to think about identity and access. Zero Trust adds the idea that access should always be verified and limited. Together, they help SOC analysts investigate suspicious logins and help cloud teams reduce the impact of compromised accounts.