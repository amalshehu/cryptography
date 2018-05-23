# Cryptography

## Basic concepts

### Cipher

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

The combination of CIA produces a complete security plan.

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
- Provides authentication and encryption

### El Gamal

- SUpports digital signature, encryption, key exchange
- Entension of Diffie-Hellman algorithm.
- Similar level of protection as RSA and ECC
- Comparitively slower.

### Strength and weakness of Asymmetric Key Cryptography

Strength

- Secure key exchange
- Simplified key management.
- Supports authentication
- Digital signature
- High level of security comparing to symmetric.

Usecases

- Key exchange
- Message encryption
- Part of web security
- Message authentication

Weakness

- Slower than symmetric key cryptography
- Recommended use along with symmetric.

## Integrity

### Hashing

Hash algorithms takes the file and generates an unique hash value.

Consider if we have a file and want to send someone else. We need make sure that the file is not modified during the transit.This can be solved by a hashing algorithm. It will take the file as input and generate a hash value. The value will be same everytime you process through the same hashing algorithm. Then we send the file to the recipent along with the hash value. The recipient runs the file through the same algorithm and checks whether it matches hash value that provided along with that file. if it matches we can assure that the file is unmodified.

### Why hash

- The main use case of hash is, it can be used as the index of a data in a database. Becuase it's really faster to find the data.
- Typical data strucutres like arrays and lists are not efficient in huge data lookup.
- Normal look-ups need to occur in near constant time. O(1)

### Collision

- When an algorithm generates same hash values for multiple values, it causes collision.
- A good hash function should handle collision.
- It can be reduced with a good selection of hash function.
- The systematic approach for adding new key after collision to the table is called collision resolution.
- Also we can implement some techniques like linear probing. (Open addressing)

### Linear probing

Linear probing is a scheme in computer programming for resolving collisions in hash tables, data structures for maintaining a collection of key–value pairs and looking up the value associated with a given key.

### Probability of collison

Can obtain equations from: https://en.wikipedia.org/wiki/Birthday_problem

### MD2, MD4 and MD5 (Message Digest algorithms)

- MD2 and MD4 are one way hash functions
- Both generates a 128 bit hash
- COmparitively similar strength.
- MD2 is slower than MD4 or MD5
- MD5 is a newer version of MD5, with additonal rounds of operation.
- Unfortunately MD5 is vulnerable to collision attacks. For insatnce if     two messages provides the same hash value.
- The main intension of a hash algorithm to create a unique hash value      that validate the information was not compromised. It's a significant     vulnerability.
- Because of this MD5 is no longer used in digital signatures or SSL.

### SHA (Secure Hashing Algorithm)

- Designed by NSA to use with Digital Signature Standard
- SHA-1 uses 160 bit and SHA-256 uses 256 bit
- SHA-1 is similar to MD4 and MD5 but stronger
- Addesses the vulnerability in MD5 collision attacks.
- As computing power increased, SHA-1 was also compromised to a collision attack in 2017.
- But SHA-256 is more better and improved.
- Now SHA-256 considered as the secure hash standard.

### HAVAL

- Based on MD5
- Stronger than MD5
- Uses variable length hashes from 128-256 bits
- Variable number of rounds
- Vulnerable to collision attacks like MD5

### Tiger

- Not based on MD5
- 192 bit hash
- Faster than SHA-1 and MD5
- Not vulnerable to collision attacks

### Digital Signatures

Digital signatures are used to validate the person's identity.

In an asymmetric cryptographic encryption, Here we will use a public key to encrypt the message and uses a private key to decrypt the message.
To add a digital signature to this process, before you encrypt the message we should run through a hash to generate a hash value. Then take the hash value and encrypt it with your private key. The result is the digital signature for our message. This value will be added to the original message, then encrypt it and trasmitted to the reciever.

On message recieve, it will decrypted and send through the same hash to genrate hash value. This hash value is decrypted using sender public key and compares to the value in senders digital signature. Then it verifies the digital signature.

- This can prove the senders identity.
- It also proves the message was unmodified after it was signed.
- Non repudiation (Ensures a person cannot deny that they were            responsible for the action.)

### Public Key Infrastructure (PKI)

PKI is a framework that provides confidentiality, integrity, authentication and non-repudiation.
