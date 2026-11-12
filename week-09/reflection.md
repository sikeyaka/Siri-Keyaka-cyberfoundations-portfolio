# Week 9 Reflection - Vault Exchange Digital Trust

**Student Name:** Siri Keyaka

**Week:** 9

1. What clicked for you this week?

```text
I now understand how digital certificates connect a public key to a verified identity through a trusted Certificate Authority (CA). Seeing the certificate chain in Chrome and testing verification with OpenSSL helped me understand how digital trust works in practice.
```

2. What's still confusing?

```text
I understand certificate validity and trust chains better, but I would like to deepen my understanding of certificate revocation, particularly how browsers determine whether a certificate has been revoked before its expiration date.
```

3. How does this week's material connect to a cybersecurity career path you're interested in?

```text
This connects to my interest in Security Operations and Incident Response because analysts investigate secure connections, certificate errors, and potential impersonation attempts. Understanding TLS and certificate verification can help me identify misconfigurations and distinguish connection problems from trust failures.
```

4. One thing you would tell a friend just starting this course:

```text
Don't assume a website is trustworthy just because your browser says the connection is secure. Understanding what a certificate actually verifies is just as important as knowing how to check it.
```

## Professional Growth Check

- [x] I can explain why a working key’s label does not prove who owns it.

- [x] I can read the digital badge and describe the list of signing offices I actually saw.

- [x] I can explain the service’s key, its badge application, the office’s key, and the finished badge.

- [x] I can explain why correct information passed and why an intentionally wrong input was refused.

- [x] I can tell the difference between a service not answering and its badge failing a check.

- [x] I can share useful screenshots while keeping private keys and passwords secret.

## Portfolio Deliverable 3 Reflection

Write 5–7 sentences. What can a correctly checked digital badge tell you about the service? What can it NOT promise? Describe one problem using the message you actually saw, and explain what you checked next. Compare the real website with your practice service. You may start with “I used to think…”, “My check showed…”, and “I now know…”.

```text
A correctly verified digital certificate helps confirm that a service's public key is associated with the expected hostname through a trusted certificate authority. However, it does not guarantee that the website's content, downloads, or services are safe. In Lab 01, I inspected a real website's certificate in Chrome to review its identity, validity dates, and chain of trust. In Lab 02, I created certificates and tested verification using OpenSSL and a local TLS service. When I tested an incorrect hostname, verification failed with error 62 (hostname mismatch). I checked the certificate's SAN and repeated the verification using the correct hostname, which passed. These exercises helped me understand the difference between inspecting an existing certificate and testing digital trust through hands-on verification.
```
