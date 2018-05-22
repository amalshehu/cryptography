# Cryptography

## Basic concepts

- Cipher

In cryptography, a cipher (or cypher) is an algorithm for performing encryption or decryption—a series of well-defined steps that can be followed as a procedure. Precisely a system used for creating secret messages. Eg: Ceasar cipher

- CIA Triad (Confidentiality, Integrity, Availability)
  - Confidentiality
    - File encryption
    - Message encryption
    - Link encryption
  - Integrity
    - Digital signatures
    - Hashes
  - Availability

## Symmetric Key Cryptography

The same key is used to encrypt and decrypt messages.
THe strength of the symetric approach comes from the key size and algorithm used.
Eg: Ceasar cipher

- Stream and block ciphers
  - Modes
  - Cipher block chaining
  - Rounds

### DES (Data encryption standard)

- National cryptographic standard in 1977
- 64 bit key
- 16 rounds of encryption
- Cracked on 1998

### 3DES

- Quick fix for DES
- 168 bit key
- 48 rounds
- Common usage: Payment cards

### AES (Advanced encryption standard)

- 128 bit, 192 bit, 265 bit can be used by the level of protection needed.
- Rounds varies by key length and bloack size
- Faster ans secure comparitively.
- Chosen to replace DES as new standard.

### RC4 (Ron's Code 4)

- It is a stream cipher used in SSL and WEP for early Wi-Fi security
- Variable key size
- Popular due to speed and simplicity

### RC 5 and RC 6

### Blowfish and Twofish

Blowfish

- It is block cipher
- Key length supported : 32bit to 448 bit.
- 16 Rounds
- Indented as a replacement for DES.
- Its free and available

Twofish

- It is one of the algorithm that considered as AES.
- 128, 192, 256 bits supported
- 16 ROunds
- Free

### Strength and weakness of Symmetric Key Cryptography

Strength

- Faster than asymmetric
- Harder to crack
- Algorithms AES 256 is very difficult to crack.
- As long asthe key is not compromised, symmetric cryptography is strong.

Use cases

- File encryption for transmission (AES 256)
- Encryption of file in storage (AES 256)
- Finantial transactions (3DES)
- VPN ENcryption (AES 256)

Weekness

- Another method needed for secure key transmission.
- Difficult key management
- No non repudiation
- No digital signature
- Lacks message security, website security
- Lacks key transfer.

Symmetric key cryptography does not provide a complete solution due to its weaknesses.

## Asymmetric Key Cryptography

- Uses private and pubic keys
- These key pairs will be used for key exchange to encrypt messages.

### Encryption and decryption

Suppose if two people are exchanging messages. They will generate a public and private key.
Then next steps would be the axchange of the public keys. The private key will be kept as secret.
If multiple poeple are communicating then all should share key with each other by creating a public key ring that all of them have access.

For encrypting a message, Will will run it throgh an asymmetic cypher using the other persons public key to encrypt.Then the message is ready to transmit over internet.

For decryption, The other person will run the message throught same cipher but use their private key to decrypt it.

### DIffie-Hellman Algorithm

- First asymmetric key agreement algorithm.
- Uses private pubic key pairs to genrate symmetric key
- The symmetric key is unique to the two people communcating with it since it can only be created by those two key pairs.
- Vulnerable to man in the middle attack.
- Need additional method of authentication to overcome the attack.

### RSA Algorithm

- Provides authenticaiton and encryption
- Can be used for encryption and digital signatures.
- Can be used for key exchangess
- One way function 
- Used in hardware devices, Eg: Smart cards

### Elliptic Curve Cryptosystem (ECC)

- Faster and more efficient than RSA
- Can provide same level of protection like RSA