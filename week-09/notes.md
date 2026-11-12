# Week 9 Notes - Vault Exchange Digital Trust

**Student Name:** Siri Keyaka

**Week:** 9

Use your own words. Short notes and everyday examples are welcome. You do not need to memorize commands.

## From a Key to an Identity

Ivy has two keys with the same label. Why is the label not enough? How can checking a visitor badge help explain the problem?

```text
My explanation: A key's label does not prove who owns it because anyone can create a key and assign it a name. A digital certificate works like a visitor badge by connecting a public key to an identity through a trusted issuing authority.
```

## Certificate Fields

A certificate is a digital badge. Explain the name list (SAN), signing office (issuer), start/end dates, public key, signature method, and allowed job (purpose). Which field would you check to see whether the badge covers the right website?

```text
Field and its job: The SAN lists the website names covered by the certificate, while the issuer identifies the CA that signed it. The validity dates show when it can be used, the public key supports cryptographic verification, the signature algorithm identifies how the CA signed it, and the Extended Key Usage specifies its permitted purpose. I would check the SAN to confirm that the certificate covers the website's hostname.
```

## Issuers and Accepted Trust

Who signed the badge? Who chooses whether to accept the top office? Explain why an office signing its own badge is not enough to make your browser trust it.

```text
My explanation: The issuing CA signs the website's certificate, and the browser uses its trusted root certificate authorities to determine whether to accept the chain. A self-signed root certificate is not automatically trusted because anyone can create one. The root must already be trusted by the browser or system, or be explicitly accepted.
```

## Key CSR and Certificate Roles

The CSR is a badge application. Explain the separate jobs of the service’s private key, application, office’s private key, and finished certificate. Who signs the application? Who signs the finished badge?

```text
My explanation: The service's private key signs the CSR, which requests a certificate containing its public key and identity information. The CA uses its own private key to sign the issued certificate after the required validation. The finished certificate connects the service's identity to its public key without exposing either private key.
```

## TLS and Verification Evidence

Compare looking at a certificate, checking its saved file, and connecting to a running service. TLS sets up a protected connection. What did you observe in each activity?

```text
I looked at: The certificate for example.com in Chrome, including its SAN, issuer, validity dates, and certificate chain.
I checked: The locally issued certificate using OpenSSL. Verification passed with the correct hostname and CA but failed with a hostname mismatch (error 62) and an unrelated CA (error 20).
I connected to: A TLS 1.3 service running on 127.0.0.1:8443. The correct hostname verified successfully, while the wrong hostname failed verification.
```

## Troubleshooting and Remediation

These words mean finding and fixing a problem. Record an actual message, what it meant, and your next step. Consider a wrong name, expired dates, wrong office, canceled certificate, or service that is not running. Label situations you only discussed; do not claim to have tested them.

```text
Message or situation: Connection refused (errno 111) after stopping the TLS listener.
What it means: No service was listening on the specified address and port, so the connection could not be established.
What I would check or fix: Check whether the TLS server is running and listening on 127.0.0.1:8443. Restart the authorized lab listener if needed.
Which check I would repeat: Repeat the ss listener check, followed by the OpenSSL TLS connection and certificate verification test.
```

## Questions I Still Have

```text
A word or step I want explained again: How does a browser determine whether a certificate has been revoked before its expiration date?
```
