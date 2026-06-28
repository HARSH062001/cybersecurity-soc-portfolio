# Security Controls Mapping

## Topic Summary

Security controls are safeguards used to reduce risk. Security+ expects you to understand different control types and why organisations layer them together. For SOC and cloud work, control mapping helps connect a security event to the right prevention, detection, and response action.

## Key Definitions

* Security control: a safeguard or countermeasure that reduces risk
* Preventive control: stops an attack before it succeeds
* Detective control: identifies suspicious or harmful activity
* Corrective control: helps fix problems after an incident
* Deterrent control: discourages attackers or policy violations
* Compensating control: an alternative safeguard used when the ideal control is not possible
* Administrative control: policy, training, standards, and procedures
* Technical control: security technology such as MFA, EDR, or firewall rules
* Physical control: locks, cameras, guards, and barriers

## Daily-Life Example

A shop might use door locks to prevent theft, CCTV cameras to detect suspicious behaviour, staff procedures to respond to incidents, and warning signs to discourage shoplifting. These all support the same security goal in different ways.

## SOC Analyst Use Case

If a phishing email reaches an inbox, a SOC analyst may map the event against controls such as email filtering, user awareness training, endpoint detection, SIEM alerts, and incident response playbooks. This helps explain what worked, what failed, and where the control gaps are.

## Cloud Security Example

In AWS, preventive controls might include restrictive IAM policies and S3 block public access. Detective controls might include CloudTrail, GuardDuty, and CloudWatch alerts. Corrective controls might include automated remediation or incident response runbooks.

## Mini Incident Scenario

An attacker uses stolen credentials to access a cloud console because MFA was not enabled on an admin account. Logs later show unusual changes to permissions.

## Practical Task or Observation Activity

1. Pick one simple incident such as a phishing click or public cloud bucket exposure.
2. List one preventive, one detective, and one corrective control for that scenario.
3. Add one administrative or training control that could reduce the same risk.
4. Decide which control failed and which control helped detect the issue.
5. Write a short summary explaining how layered controls reduce business impact.

## Exam Traps

* Control categories can overlap. A firewall is usually a technical preventive control, but logs from it can also support detection.
* Administrative, technical, and physical describe control form, while preventive or detective describe control purpose.
* Compensating controls do not mean weak controls. They are alternate measures when the preferred control cannot be used.
* A single control is rarely enough. Security exams often test layered defence.

## What I Learned

Control mapping helps turn theory into practical analysis. It gives me a way to explain incidents, identify missing safeguards, and understand how SOC monitoring and cloud security controls work together.