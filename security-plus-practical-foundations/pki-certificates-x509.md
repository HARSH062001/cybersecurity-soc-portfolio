# PKI, X.509, and Certificates

## Topic Summary

Public Key Infrastructure (PKI) is the system used to create, manage, distribute, and trust digital certificates. X.509 is the standard format used by most certificates on the internet and in enterprise environments. These topics matter in Security+ because they connect trust, encryption, identity, and secure communication.

## Key Definitions

* PKI: the framework of certificate authorities, certificates, policies, and processes used to manage digital trust
* Certificate authority (CA): a trusted entity that issues and signs digital certificates
* X.509 certificate: the common certificate format used for TLS, websites, devices, and many enterprise systems
* Public key: the key shared openly for encryption verification or secure communication
* Private key: the secret key that must be protected
* Certificate signing request (CSR): a request used to apply for a certificate
* Revocation: invalidating a certificate before it expires
* TLS: the protocol used to secure network communication such as HTTPS

## Daily-Life Example

A passport works because a trusted government authority issues it and other organisations accept that trust. A digital certificate works in a similar way because a trusted certificate authority signs it, and systems use that trust to validate identity.

## SOC Analyst Use Case

A SOC analyst may investigate a phishing site that uses a valid TLS certificate to appear legitimate. The analyst may also review certificate warnings, expired certificates, or suspicious certificate changes during an incident to decide whether users were exposed to spoofed infrastructure.

## Cloud Security Example

Cloud applications often use certificates for HTTPS on load balancers, web servers, APIs, and internal services. In AWS, teams may use ACM to manage certificates for public services. Strong certificate management supports trusted encryption and reduces service outages caused by expired certificates.

## Mini Incident Scenario

Users begin receiving browser warnings when connecting to an internal portal. Investigation shows the TLS certificate expired two days ago, and the service owner did not renew it on time.

## Practical Task or Observation Activity

1. Visit a trusted HTTPS website and inspect the certificate details in the browser.
2. Identify the certificate subject, issuer, and expiry date.
3. Note whether the certificate is being used to support server identity and encrypted communication.
4. Write a short explanation of why an expired or revoked certificate is a security and availability risk.
5. Compare how a valid certificate helps users trust a site, but does not guarantee the site is harmless.

## Exam Traps

* A certificate proves a trusted relationship, not that a website is automatically safe.
* Public key and private key roles are easy to mix up, especially in signature and encryption questions.
* Expired and revoked certificates are different. Expired means the time ended, while revoked means trust was removed early.
* PKI is broader than just HTTPS websites. It also applies to devices, email, VPNs, and enterprise identity systems.

## What I Learned

PKI explains how trust is built into secure communication. Understanding certificates and X.509 helps me read alerts more confidently, investigate suspicious web activity, and connect exam concepts to real SOC and cloud security work.