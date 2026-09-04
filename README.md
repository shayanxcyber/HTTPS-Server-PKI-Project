# HTTPS Server and Private PKI Lab

A hands-on university lab exploring how a private certificate authority establishes trust for an HTTPS service. The
work was completed for UTS 41900 Cryptography using Linux, SSH and the OpenSSL command-line tools.

## What the lab demonstrates

1. Configuring an OpenSSH server and testing local access.
2. Generating an RSA key pair for SSH public-key authentication.
3. Creating a private root certificate authority and self-signed X.509 root certificate.
4. Generating a server key and certificate-signing request.
5. Signing the server certificate with the private CA.
6. Starting an HTTPS test service with `openssl s_server`.
7. Importing the lab CA into a browser trust store and validating the resulting HTTPS connection.

```text
Private root CA
      |
      | signs
      v
Server certificate + server private key
      |
      | presented by
      v
Local OpenSSL HTTPS service
      |
      | validated against imported lab CA
      v
Browser client
```

## Evidence

The [full lab report](docs/PKI-and-HTTPS-Lab-Report.pdf) records the commands, certificate output and browser
validation from the exercise.

> All keys and certificates displayed in the report are disposable educational-lab artefacts and were not used to
> protect production systems or real data.

## Technologies and concepts

- OpenSSL and X.509 certificates
- public key infrastructure and certificate signing
- TLS/HTTPS trust validation
- SSH public-key authentication
- Linux service configuration

## Scope

This is a learning record from a controlled university environment. It demonstrates the certificate lifecycle and
chain-of-trust workflow; it is not a reusable production PKI deployment.

