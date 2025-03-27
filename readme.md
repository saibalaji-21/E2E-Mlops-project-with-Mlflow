
# Secure Key Management System

## Overview
This project implements a Secure Key Management System (KMS) that handles both symmetric and asymmetric encryption. It is designed to meet the following requirements:
- **Centralized Key Distribution:** AES keys are generated and stored in a centralized repository.
- **Public Key Infrastructure (PKI):** RSA key pairs are generated for asymmetric encryption, simulating a PKI.
- **Secure Key Generation and Storage:** Uses secure random number generation and industry-standard cryptographic libraries.
- **Secure Key Exchange:** Implements Diffie-Hellman key exchange to derive ephemeral session keys ensuring forward secrecy.
- **Key Revocation:** Provides a mechanism to revoke (delete) keys in case of compromise.

## Features
- **Symmetric Encryption (AES):**
  - 256-bit key generation.
  - AES encryption in CBC mode with PKCS7 padding.
- **Asymmetric Encryption (RSA):**
  - 2048-bit RSA key pair generation.
  - Encryption and decryption using PKCS1v15 padding.
- **Diffie-Hellman Key Exchange:**
  - Generation of ephemeral DH keys for secure session key derivation.
- **Key Revocation:**
  - Simple mechanism to remove compromised keys from the system.

## Requirements
- Python 3.6+
- [cryptography](https://cryptography.io/en/latest/) library

## Installation
1. **Clone the repository:**
```bash
   git clone https://github.com/yourusername/secure-key-management.git
   cd secure-key-management
```
2. Install dependencies:
```bash
pip install cryptography
```
## How to Run
Simply execute the Python file containing the implementation. For example:
```bash
python secure_key_mgmt.py
```
This will run the test cases provided at the end of the file:
- AES encryption/decryption test.
- RSA encryption/decryption test.
- Diffie-Hellman key exchange test.
- Key revocation test (including a test case to check that decryption fails after revocation).

## Code Structure
- **SecureKeyManagementSystem Class:**
  Contains methods for:
  - Generating AES keys (generate_aes_key)
  - Generating RSA key pairs (generate_rsa_key_pair)
  - Encrypting and decrypting data using AES (encrypt_with_aes, decrypt_with_aes)
  - Encrypting and decrypting data using RSA (encrypt_with_rsa, decrypt_with_rsa)
  - Generating Diffie-Hellman keys (generate_diffie_hellman_key)
  - Revoking keys (key_revocation)

- **Test Cases:**
  At the bottom of the file, several test cases demonstrate how to:
  - Manage symmetric encryption.
  - Manage asymmetric encryption.
  - Execute Diffie-Hellman key exchange.
  - Revoke keys and handle errors when using revoked keys.

## Security Considerations
- **Mitigation of MITM Attacks:**
  Although this implementation simulates a PKI, a production system would integrate a Certificate Authority (CA) and use TLS/SSL for secure communication.
- **Forward Secrecy:**
  Ephemeral Diffie-Hellman keys ensure that even if long-term keys are compromised, past communications remain secure.
- **Key Revocation:**
  The simple key revocation mechanism allows deletion of keys if they are found to be compromised, reducing the risk of unauthorized data decryption.

## Link to Codespaces
You can run this code in codespaces through the following link:
https://effective-bassoon-4jjwjr69xrv92756r.github.dev/
