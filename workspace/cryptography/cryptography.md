# Cryptography

- [x] Symmetric
- [x] Asymmetric

## Encryption

- [x] Plain-text to cipher-text

## Decryption

- [x] Cipher-text to plain-text

## Government Access to Keys

GAK is a cryptographic concept where the government has full or partial access to private and public keys, which are only used or released under specific circumstances when a court warrant is issued. This is known as a **key escrow**(digital forensics purpose).

## Encryption Algorithms

Here’s a comparative table highlighting the key differences between symmetric and asymmetric encryption:

| Feature / Attribute         | Symmetric Encryption                       | Asymmetric Encryption                    |
|------------------------------|-------------------------------------------|------------------------------------------|
| **Key Usage**               | Same key for encryption and decryption    | Two keys: a public key (for encryption) and a private key (for decryption) |
| **Key Management**          | More challenging due to key distribution and management | Easier key management since only the public key is shared |
| **Speed**                   | Generally faster; suitable for large amounts of data | Slower; more computationally intensive |
| **Security Level**          | Depends on key length; shorter keys can be vulnerable | Generally stronger; relies on mathematical problems (e.g., factoring, discrete logs) |
| **Common Algorithms**       | AES, DES, RC4, Blowfish                   | RSA, DSA, ECC (Elliptic Curve Cryptography) |
| **Use Cases**               | Data encryption (files, databases, communications) | Secure key exchange, digital signatures, secure communication protocols (e.g., SSL/TLS) |
| **Scalability**             | Less scalable for large systems due to secret key sharing | More scalable; public keys can be distributed to anyone without security risk |
| **Overhead**                | Lower overhead in terms of processing      | Higher overhead due to the complexity of the algorithms |
| **Example of Process**      | Encrypts and decrypts data using a shared secret | Data encrypted with a public key can only be decrypted with the private key |

### Summary

- **Symmetric Encryption**: Involves a single shared key for both encryption and decryption, making it efficient but more complex to distribute securely.
- **Asymmetric Encryption**: Utilizes a pair of keys (public and private), enhancing security and ease of key management but generally at the cost of computational efficiency.

Both symmetric and asymmetric encryption approaches play vital roles in securing communications, often working together in practice, such as using asymmetric encryption to securely exchange symmetric keys. If you have further questions or need additional details, feel free to ask!

### DES

<p align="center">
  <img src="..\assets\images\des.jpg" alt="DES[1]">
</p>

- [x] 8 bit for parity bits

> After verification 8 bit for parity bits will be dropped.

### AES

<p align="center">
  <img src="..\assets\images\aes.jpg" alt="AES[1]">
</p>

- [x] 10 rounds for 128-bit keys
- [x] 12 rounds for 192-bit keys
- [x] 14 rounds for 256-bit keys

### RC 4/5

<p align="center">
  <img src="..\assets\images\rc.jpg" alt="RC[1]">
</p>

### DSA

<p align="center">
  <img src="..\assets\images\dsa.jpg" alt="DSA[1]">
</p>

### Comparison

Here’s a comparative table for RSA, AES, DES, RC4, RC5, and DSA, highlighting their key features, types, strengths, and weaknesses.

| Feature / Attribute          | RSA                              | AES                          | DES                              | RC4                          | RC5                          | DSA                             |
|------------------------------|----------------------------------|-----------------------------|----------------------------------|-----------------------------|-----------------------------|---------------------------------|
| **Type**                     | Asymmetric encryption             | Symmetric encryption        | Symmetric encryption              | Stream cipher               | Symmetric encryption        | Digital Signature Algorithm     |
| **Key Length**               | Typically 1024-4096 bits         | 128, 192, or 256 bits      | 56 bits (effective key size)     | Variable (up to 256 bits)   | 0-2040 bits (commonly 128/256) | Typically 1024-3072 bits       |
| **Block Size**               | N/A                              | 128 bits                    | 64 bits                          | N/A                         | 32, 64, 128, 256 bits      | N/A                             |
| **Security Level**           | Strong (based on factorization)  | Strong (currently secure)   | Weak (vulnerable to brute-force) | Weak (vulnerable to attacks)| Moderate to strong          | Strong (depends on key length) |
| **Speed**                    | Slower (computationally intensive)| Fast                        | Fast                            | Very fast                  | Fast                        | Slow (performance varies)      |
| **Use Cases**                | Secure key exchange, digital signatures | Data encryption            | Legacy systems, file encryption   | Network communication       | High-performance encryption  | Digital signatures, authentication |
| **Initial Release**          | 1977                             | 2001                        | 1977                             | 1987                       | 1994                        | 1991                            |
| **Major Vulnerabilities**     | Vulnerable to quantum attacks    | Not publicly known          | Vulnerable to brute-force and weak keys | Weak key management      | Weak against certain attacks | Vulnerable to small key sizes   |
| **Algorithm Structure**      | Based on modular arithmetic       | Substitution-permutation network | Feistel network                | None (stream cipher)       | Feistel network             | Uses modular exponentiation      |
| **Current Status**           | Still widely used                | Recommended for new systems | Deprecated for secure systems    | Deprecated for secure use   | Commonly used but has vulnerabilities | Widely used in security protocols |

### Notes

1. **RSA**: Primarily used for secure data transmission and digital signatures. Its security relies on the difficulty of factoring large integers.
2. **AES (Advanced Encryption Standard)**: A widely used symmetric encryption standard that is considered secure and efficient.
3. **DES (Data Encryption Standard)**: An older symmetric encryption algorithm that has largely been replaced by AES due to security vulnerabilities.
4. **RC4**: A stream cipher that was widely used but has well-documented vulnerabilities, making it unsuitable for new applications.
5. **RC5**: A flexible block cipher that allows for variable block sizes and key lengths, but may also have vulnerabilities under certain conditions.
6. **DSA (Digital Signature Algorithm)**: Used for digital signatures and relies on discrete logarithms for security. Key length must be sufficiently large to ensure security.

## Hashing

<p align="center">
  <img src="..\assets\images\hash.jpg" alt="Hash[1]">
  HAsh
</p>

<p align="center">
  <img src="..\assets\images\md5.jpg" alt="MD5[1]">
  MDF
</p>

Here's a comparative table of Hash1 and Hash2 vs. Message Digest (MD) algorithms. I'll consider "Hash1" as a general reference to any hashing algorithm and "Hash2" similarly. However, for the purpose of clarity, I'll provide details typically related to known hashing algorithms such as SHA-1 (Hash1), SHA-256 (Hash2), and Message Digest 5 (MD5).

Here’s an updated comparative table that includes multiple hashing algorithms, including the previously mentioned SHA-1, SHA-256, and MD5, as well as other commonly used hash functions like SHA-512, SHA-3, and BLAKE2.

| Feature / Attribute         | SHA-1                        | SHA-256                     | MD5                          | SHA-512                      | SHA-3                       | BLAKE2                      |
|-----------------------------|------------------------------|-----------------------------|------------------------------|------------------------------|-----------------------------|-----------------------------|
| **Algorithm Type**          | Cryptographic hash function   | Cryptographic hash function  | Cryptographic hash function   | Cryptographic hash function   | Cryptographic hash function  | Cryptographic hash function  |
| **Output Size**             | 160 bits (20 bytes)          | 256 bits (32 bytes)         | 128 bits (16 bytes)          | 512 bits (64 bytes)          | Variable (e.g., 224, 256, 384, 512 bits) | Variable (up to 512 bits)   |
| **Security Level**          | Weak (vulnerable to collisions) | Strong (generally considered secure) | Weak (vulnerable to collisions) | Strong (more secure than SHA-256) | Strong (designed for security) | Very strong (faster and highly secure) |
| **Applications**            | Digital signatures, certificate generation | Data integrity, cryptographic applications, digital signatures | Checksums, data integrity verification | Data integrity, cryptographic applications | Digital signatures, data integrity | General-purpose hashing, password hashing |
| **Performance**             | Faster than SHA-256 but slower than MD5 | Slower than SHA-1 and MD5    | Fastest among the three       | Slower than SHA-256 and SHA-1 | Fast, optimized for performance | Extremely fast               |
| **Collision Resistance**    | Vulnerable (collisions found in 2017) | Strong collision resistance   | Vulnerable (collisions found) | Strong collision resistance    | Strong collision resistance   | Strong collision resistance   |
| **Preimage Resistance**     | Moderate                      | Strong                       | Moderate                      | Strong                       | Strong                       | Strong                       |
| **Usage Status**            | Deprecated for security-sensitive applications | Recommended for secure applications | Deprecated for security-sensitive applications | Recommended for secure applications | Recommended for secure applications | Recommended for general use  |

### Additional Notes

1. **Security Vulnerabilities**: SHA-1 and MD5 are considered obsolete for secure applications due to vulnerabilities (collisions, preimage attacks, etc.). SHA-256 and SHA-512 are part of the SHA-2 family, while SHA-3 represents the latest standard, designed to address some of the weaknesses of its predecessors.
2. **Performance**: While MD5 is the fastest due to its shorter output size, it should not be used for security purposes. BLAKE2 is designed to be faster than MD5 while still being cryptographically secure.
3. **Usage Recommendations**: For secure applications, prefer SHA-256, SHA-512, SHA-3, or BLAKE2. The choice may depend on the specific performance and security requirements of your application.


## Password

<p align="center">
  <img src="..\assets\images\argon.jpg" alt="Pass">
  HAsh
</p>


## Cryptography Tools

Here's a structured table summarizing the key points regarding security concepts mentioned:

| **Security Component**            | **Description**                                                                                                                                                       |
|-----------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Security Token**                | The security token, also known as the authentication token, is used to authenticate users and provide statefulness to the HTTP protocol. It is essential for maintaining secure sessions and must be encrypted to ensure secure data exchange. |
| **Microsoft's CertMgr.exe**      | A cryptography tool provided by Microsoft for the creation and management of digital certificates. These certificates are essential for ensuring secure communication and data protection between parties.                          |
| **JSA (Java Security Architecture)** | A library used in Java for implementing security features, including authentication, access control, and cryptography, ensuring robust security measures within Java applications.                                    |
| **Docker**                        | Docker provides an encrypted data store for containerized applications, enhancing the security of data transferred and stored within Docker containers, ensuring that sensitive information is protected.                   |
| **SignTool.exe**                 | A Microsoft tool used for digitally signing files. It helps in verifying the integrity and authenticity of files and software, ensuring that they have not been tampered with and are from a trusted source.                 |
| **Authentication using Keys**     | Authentication can be achieved using two types of cryptographic keys: asymmetric (public/private key pairs) and symmetric (same key for encryption and decryption), each serving different use cases and security levels. |

