# [Cryptography] Cryptosystem Types
*Learn about modern cryptosystems that are in use today.*

![banner alt text](.rsrc/banner.png)

# Objectives
- Symmetric vs asymmetric cryptography (public key)
- Symmetric (AES)
- Asymmetric (RSA, diffie-hellman, elliptic curve)

# Introduction
In a previous lesson, we talked about several primitive cryptosystems. Now, we will cover modern systems that are in use today. Modern cryptography is often categorized as symmetric or asymmetric cryptography. Symmetric cryptography requires both the sender and receiver of an encrypted message to have a shared private key. In asymmetric cryptography, the sender and receiver each have a public and a private key, and only need to share their public keys in order to exchange encrypted messages. 

In this lesson, we will cover the basics of a few types of symmetric (AES) and asymmetric (RSA, Diffie-Hellman, Elliptic Curve) cryptosystems. 

# Lesson
## Symmetric Cryptosystems

In a symmetric cryptosystem, both the sender and receiver of an encrypted message needs to know the private key. Prior to sending and receive any secure messages, both parties must find a way to securely decide upon a private key. In the example below, Alice is sending an crypted message to Bob. 

![Sending a Message with Symmetric Cryptography](.rsrc/symmetric-crypto.png)

Alice encrypts a plaintext message with the shared single private key, resulting in a ciphertext message. This encrypted ciphertext message is sent to Bob. Bob decrypts the ciphertext message with the same private key, allowing him to recover the plaintext message sent by Alice. 

### AES
Advanced Encryption Standard (AES) is a type of symmetric cryptography, where the same private key is used to encrypt and decrypt a message. Currently, it would take billions of years to use a brute-force attack against the AES algorithm. However, a less sophisticated way that an attacker could break AES security is by stealing improperly protected private keys. For example, if Alice simply sent an unencrypted message to Bob with the private key so that they can both share it, an attacker might be able to intercept this message and thus be able to decrypt any future encrypted messages sent between Alice and Bob. 

## Asymmetric Cryptosystems

In an asymmetric cryptosystem, also known as a public-key cryptosystem, both the sender and receiver each have a private and a public key. Each person can generate their own private and public key pair. Each person should always keep their private key private, but can freely distribute their public key without any negative consequences. In the example below, Alice sends an encrypted message to Bob using an asymmetric cryptosystem. 

![Sending a Message with Asymmetric Cryptography](.rsrc/asymmetric-crypto.png)

In this example, Bob has shared his public key with Alice and keeps his private key private. Alice uses Bob's public key to encrypt a plaintext message, resulting in an encrypted ciphertext message. This encrypted message is sent to Bob. Bob then uses his private key to decrypt the ciphertext into Alice's original plaintext message. In this example, Alice's public and private keys are not needed since she is sending a message to Bob. If Bob wanted to send an encrypted message back to Alice, he would then need her public key, and Alice would use her private key to decrypt a message from Bob. 

### RSA
Rivest-Shamir-Adleman (RSA) is a type of asymmetric encryption that uses a private and public key based on two large prime numbers. The algorithm for encryption involves multiplying two very large prime numbers, and is considered very hard to crack because recovering the two original prime numbers is a mathematical problem that is currently thought to be infeasible to solve efficiently. There are some known attacks against RSA, but many of these attacks occur when small prime numbers are used. For example, if small prime numbers are used, an attacker could brute force factoring the two prime numbers. 

### Diffie-Hellman
The Diffie-Hellman key exchange process involves the use of asymmetric encryption, and is used to establish a shared private key for use in future communications. When we previously talked about AES (symmetric cryptosystem), we noted that Alice and Bob would need a way to securely share a private key. The Diffie-Hellman key exchange process can accomplish this. The Diffie-Hellman algorithm involves a public modulus and base value, and two secret values chosen by Alice and Bob. Through an elegant mathematical algorithm, Alice and Bob can each use their own private secret values to calculate a public key that can be shared with anyone. Anyone can then use Alice's public key to encrypt a message that only she will be able to decrypt, with her private key. As long as the private key stays private to her, no one else will be able to decrypt that message.

The strength of the Diffie-Hellman key exchange process depends on using a strong random number generator to choose the public modulus so that it cannot be easily predicted by an attacker. Note that the random number generator must choose only prime numbers since the public modulus must be a prime number. In addition, this process does not provide any method of authentication between Alice and Bob, so it is vulnerable to a man-in-the-middle attack where an attacker could intercept information between Alice and Bob and instead establish two separate Diffie-Hellman key exchanges with Alice and Bob. 

### Elliptic Curve Cryptosystem
Elliptic Curve Cryptosystems (ECC) are the most powerful type of cryptography currently used today. ECC is based on a mathematical concept called an elliptic curve, which is a set of points that satisfy a specific mathematical equation. For example, an elliptic curve is shown below. 


![Sample Elliptic Curve (https://blog.cloudflare.com/a-relatively-easy-to-understand-primer-on-elliptic-curve-cryptography/)](.rsrc/elliptic-curve.png)

ECC is based on solving a challenging mathematical problem that is considered more difficult to solve and more computationally expensive than the mathematical problem that RSA and Diffie-Hellman are based on. With ECC, smaller keys will achieve the same level of security compared to RSA, thus making ECC more efficient. In addition, there is also Elliptic Curve Diffie-Hellman (ECDH), which is also a key exchange protocol like Diffie-Hellman, but uses an elliptic curve public and private key pair instead. 

## Symmetric vs Asymmetric Cryptography
We previously discussed various symmetric and asymmetric cryptosystems. Below is a chart showing quick comparisons of some key features of both types of cryptosystems.

|                       |Symmetric                                                  |Asymmetric|
|-----------------------|-----------------------------------------------------------|----------|
|**Key**                |Shared private key for encryption and decryption           |Individual public key for encryption, individual private key for decryption|
|**Speed**              |Faster                                                     |Slower|
|**Key Distribution**   |Requires secure key distribution of the shared private key |Secure key distribution is not necessary since disclosure of public keys does not impact security of encrypted messages and private keys never need to be shared|
|**Examples**           |AES                                                        |RSA, Diffie-Hellman, ECC|


# Check YoSelf
## Q1 - T/F: ECC uses smaller keys than RSA for the same level of security.  
a. True <---<br>
b. False <br>

## Q2 - T/F: Symmetric cryptosystems use a key pair for the sender and receiver. 
a. True <br>
b. False <---<br>

## Q3 - Which of the following keys are used when Alice sends a message to Bob using asymmetric encryption? 
a. Alice uses her public key to encrypt the message, then Bob uses Alice's private key to decrypt the message. <br>
b. Alice uses Bob's public key to encrypt the message, then Bob uses his private key to decrypt the message. <---<br>
c. Alice uses her private key to encrypt the message, then Bob uses his private key to decrypt the message. <br>
d. Alice uses her public key to encrypt the message, then Bob uses his private key to decrypt the message. <br>

# Keep Going, Next Steps
Check out the following curated resources if you'd like to keep learning about this topic to dominate hard challenges.

1. AES Encryption - https://www.youtube.com/watch?v=O4xNJsjtN6E
2. RSA Encryption - https://www.youtube.com/watch?v=JD72Ry60eP4
3. Diffie-Hellman Key Exchange - https://www.youtube.com/watch?v=M-0qt6tdHzk
4. Elliptic Curves - https://www.youtube.com/watch?v=NF1pwjL9-DE
5. Cache-timing Attacks on AES - https://cr.yp.to/antiforgery/cachetiming-20050414.pdf
6. POODLE Attack - https://en.wikipedia.org/wiki/POODLE
