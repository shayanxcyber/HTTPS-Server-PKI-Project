# Project: Implementing a Secure HTTPS Server with a Custom Certificate Authority

This repository documents a hands-on project from the **41900 Cryptography** course, focused on the practical application of Public Key Infrastructure (PKI) to secure a web service with TLS/HTTPS.

The project involved the entire lifecycle of certificate management: from creating a private Root Certificate Authority (CA) to issuing a server certificate, deploying it on a web server, and verifying the secure connection. The primary tool used for all cryptographic operations was the industry-standard **OpenSSL** command-line interface.

### Project Workflow & Key Stages

The project was broken down into four distinct parts, demonstrating a layered approach to secure communications:

**1. Secure Shell (SSH) Configuration:**
*   Established a baseline for secure remote access by setting up an SSH server on a Linux VM.
*   Implemented both password-based and the more secure **public-key authentication**, demonstrating the use of RSA key pairs (`ssh-keygen`) for passwordless login.

**2. Private Certificate Authority (CA) Creation:**
*   Acted as a private Root CA, the trust anchor for the custom PKI environment.
*   Generated a 2048-bit RSA key pair (`ca.key`) and a self-signed X.509 root certificate (`ca.crt`) using OpenSSL. This is the foundation of the chain of trust.

**3. Server Certificate Generation & Signing:**
*   Generated a unique RSA key pair for the web server (`server.key`).
*   Created a Certificate Signing Request (CSR) (`server.csr`) containing the server's identity information (e.g., Common Name: `utscrypto.com.au`).
*   Used the private CA created in Stage 2 to **sign the server's CSR**, issuing a valid, trusted X.509 certificate (`server.crt`).

**4. HTTPS Server Deployment & Testing:**
*   Ran a simple HTTPS server using `openssl s_server`, configured to use the newly signed server certificate and private key.
*   Imported the custom Root CA certificate into a browser's trust store to resolve the "unknown issuer" error.
*   Successfully connected to the server via `https://utscrypto.com.au:4433` and verified the secure connection, indicated by the browser's padlock icon.

### Core Skills & Technologies Demonstrated:

*   **Public Key Infrastructure (PKI):** Deep, practical understanding of the chain of trust, root CAs, and certificate signing.
*   **TLS/SSL & HTTPS:** Hands-on implementation of the protocol that secures web traffic.
*   **OpenSSL:** Proficiency in using the command-line tool for key generation, CSR management, and certificate creation.
*   **X.509 Certificates:** Knowledge of certificate structure, including subjects, issuers, and public keys.
*   **Secure Server Configuration:** Basic deployment of secure services on a Linux environment.
*   **SSH & Public-Key Authentication:** Securing remote administrative access.

---
*This project was completed as part of the 41900 Cryptography course. The full report is included in this repository.*
