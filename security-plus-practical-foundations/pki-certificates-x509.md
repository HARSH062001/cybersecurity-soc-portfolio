# PKI, X.509, and Certificates

## Topic Summary

Public Key Infrastructure (PKI) is the system used to create, manage, distribute, validate, and revoke digital certificates. X.509 is the standard certificate format used by most websites, cloud services, enterprise devices, VPNs, and identity systems.

These topics matter in Security+ because they connect trust, encryption, identity, secure communication, and certificate lifecycle management.

For SOC analysts, certificate knowledge is useful when investigating phishing websites, expired certificates, suspicious certificate issuers, TLS warnings, man-in-the-middle risks, and service outages caused by certificate problems.

## Key Definitions

* **PKI:** the framework of certificate authorities, certificates, keys, policies, and processes used to manage digital trust.
* **Certificate authority (CA):** a trusted entity that issues and signs digital certificates.
* **Root CA:** the top-level trusted certificate authority in a certificate chain.
* **Intermediate CA:** a CA between the root CA and the end-entity certificate.
* **X.509 certificate:** the common certificate format used for TLS, websites, devices, and enterprise systems.
* **Public key:** the key shared openly for encryption verification or secure communication.
* **Private key:** the secret key that must be protected.
* **Certificate signing request (CSR):** a request used to apply for a certificate.
* **Revocation:** invalidating a certificate before it expires.
* **Certificate revocation list (CRL):** a list of revoked certificates.
* **OCSP:** Online Certificate Status Protocol, used to check certificate revocation status.
* **TLS:** the protocol used to secure network communication such as HTTPS.
* **Subject Alternative Name (SAN):** a certificate field that lists additional domain names covered by the certificate.
* **Wildcard certificate:** a certificate that can cover multiple subdomains, such as `*.example.com`.

## Daily-Life Example

A passport works because a trusted government authority issues it and other organisations accept that trust. A digital certificate works in a similar way because a trusted certificate authority signs it, and browsers or systems use that trust to validate identity.

## SOC Analyst Use Case

A SOC analyst may investigate a phishing site that uses a valid TLS certificate to appear legitimate. The analyst may also review certificate warnings, expired certificates, suspicious certificate changes, or unexpected certificate issuers during an incident.

Important SOC lesson: a valid certificate means the connection can be encrypted and the domain identity can be verified, but it does not automatically mean the website is safe or trustworthy.

SOC analysts may check certificates when investigating:

* phishing domains
* suspicious HTTPS websites
* expired certificate alerts
* TLS inspection issues
* certificate chain errors
* unexpected certificate issuer changes
* browser security warnings
* possible man-in-the-middle activity

## Cloud Security Example

Cloud applications often use certificates for HTTPS on load balancers, web servers, APIs, and internal services. In AWS, teams may use AWS Certificate Manager (ACM) to manage certificates for public services. Strong certificate management supports trusted encryption and reduces service outages caused by expired certificates.

Cloud examples include:

* TLS certificates on web applications
* HTTPS certificates on load balancers
* certificate renewal monitoring
* certificate validation for APIs
* certificate-based authentication for internal services
* expired certificate alerts affecting availability

## Mini Incident Scenario

Users begin receiving browser warnings when connecting to an internal portal. Investigation shows the TLS certificate expired two days ago, and the service owner did not renew it on time.

This creates both a security and availability problem. Users may ignore browser warnings, attackers may take advantage of confusion, and the service may become unavailable or untrusted.

## Practical Task: Inspecting GitHub's TLS Certificate

I inspected the certificate for `https://github.com` using the browser certificate viewer.

### Certificate Details Observed

| Field | Value |
|---|---|
| Website | `github.com` |
| Issued to | `github.com` |
| Issued by | `Sectigo Public Server Authentication CA DV E36` |
| Certificate authority organisation | `Sectigo Limited` |
| Valid from | Tuesday, May 5, 2026 at 10:00 AM |
| Valid until | Monday, August 3, 2026 at 9:59 AM |
| Certificate chain | Sectigo Public Server Authentication Root E46 → Sectigo Public Server Authentication CA DV E36 → github.com |

## Practical Observation

The certificate viewer showed a certificate chain from a trusted Sectigo root certificate to an intermediate certificate authority and then to `github.com`. This helped me understand how browsers build trust using a chain of certificates.

The certificate also showed a validity period. If a certificate expires, browsers can warn users and the service may appear unsafe or become inaccessible. This is why certificate lifecycle management is important for both security and availability.

## Exam Traps

* A certificate proves a trusted relationship, not that a website is automatically safe.
* Public key and private key roles are easy to mix up, especially in signature and encryption questions.
* Expired and revoked certificates are different. Expired means the certificate validity period ended. Revoked means trust was removed before expiry.
* PKI is broader than HTTPS websites. It also applies to devices, email, VPNs, and enterprise identity systems.
* SAN certificates and wildcard certificates are different. SAN certificates list multiple names, while wildcard certificates cover many subdomains under one domain pattern.
* A root CA is not the same as an intermediate CA.

## Interview Explanation

PKI is the trust system behind digital certificates. A browser trusts a website certificate because it can validate a chain from the website certificate back to a trusted root certificate authority. In SOC work, certificate knowledge helps investigate phishing sites, browser warnings, suspicious TLS changes, and service outages caused by expired certificates.

## What I Learned

PKI explains how trust is built into secure communication. Inspecting GitHub's certificate helped me understand the certificate subject, issuer, validity period, and certificate chain. This connects Security+ theory to real SOC and cloud security work because analysts often need to interpret certificate alerts, investigate suspicious websites, and understand HTTPS trust.
