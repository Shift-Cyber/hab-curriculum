# [Cryptography] Hashing, Checksums, and Salts
*What is data integrity and how is it verified?*

![banner alt text](.rsrc/banner.png)

# Objectives
- Student can describe why checksums are used: data integrity, errors in data transmission can occur
- Student can describe why hashes are used: data integrity, improving security of storage of passwords
- Student can distinguish between hashes and checksums
- Student can identify key the following properties of cryptographic hashing functions: non-reversibility (hashing should be a one way function, meaning you can't get the original input from the hash), diffusion or avalanche effect (making a small change in the input should result in a large change in the hash), determinism (the same string should generate the same hash), uniformity or collision avoidance (should be a good distribution), non-predictability (you should not be able to guess the hash from the string)
- Student recognizes some of the popular hashing algorithms: MD5, SHA family
- Student can define what a salt is and why it is important in the context of password storage (salts are a randomized chuck of data that is added to what you are hashing --> this will cause 2 passwords that are the same to have 2 different hashes)

# Introduction
Introduction between 100-150 words.

1. Cryptographic Hashes
2. Common Cryptographic Hashes
3. Applications of Cryptographic Hashes
4. Password Salting

# Lesson
## Cryptographic Hashes
A cryptographic hash function is an algorithm that uses a one-way function to convert a message of any size into a hash value of a fixed size, such that it is not possible to reverse the hash value back to the original message. The idea is that different messages or different lengths that get cryptographically hashed will all result in a hash value of the same length but are different. Thus, if you have a hash value to look at, there is no easy way to determine what the original message was, or how long the original message was. In addition, another key feature of a cryptographic hash is that the hash values for two very similar messages should be very different.  

For example, a hash of the message "hello there" might look something like this: **161bc25962da8fed6d2f59922fb642aa** or **6e71b3cac15d32fe2d36c270887df9479c25c640**

## Common Cryptographic Hashes
Some of the most common cryptographic hashes include MD5, SHA-1, SHA-256, and SHA-512. These are all different algorithms, that use different mathematical principles to calculate a hash value from an input message. 

For example, the table below shows the hash values of the message "hello there" using the different cryptographic hashes. 

|Cryptographic Hash Algorithm  |Hash Value                                                                                                                       |
|------------------------------|---------------------------------------------------------------------------------------------------------------------------------|
|MD5                           |161bc25962da8fed6d2f59922fb642aa                                                                                                 |
|SHA-1                         |6e71b3cac15d32fe2d36c270887df9479c25c640                                                                                         |
|SHA-256                       |12998c017066eb0d2a70b94e6ed3192985855ce390f321bbdb832022888bd251                                                                 |
|SHA-512                       |b7e98c78c24fb4c2c7b175e90474b21eae0ccf1b5ea4708b4e0f2d2940004419edc7161c18a1e71b2565df099ba017bcaa67a248e2989b6268ce078b88f2e210 |

You can see that each of these cryptographic hash algorithms results in a different length of hash value. Looking at the length of a hash can help indicate which hash algorithm was used. There are also many online tools and command line tools that can help identity the type of hash you have, and potentially what the original message was. For example, [hashes.com](https://hashes.com/en/tools/hash_identifier) guesses what type of hash algorithm was used, and sometimes guesses what the original message was. You may wonder how this site is able to guess what the original message was after our discussion of how you should not be able to guess what an original message is from a hash value. Although there is no easy way to reverse a hash value to the original message, many people have generated large lists of messages and their corresponding hash values. Generally, these lists are meant to help with stealing passwords, with many lists storing values of common passwords and their corresponding hash values. From these lists, you can then take a hash value, and find the corresponding password (original message). 

## Applications of Cryptographic Hashes
Cryptographic hashes are often used as a checksum to verify message integrity or for password verification. 

A checksum, which is the hash of a message, is often used to verify that a message being sent is not corrupted during the transmission of the message. If the sender and receiver of the message both generate the same checksum from the message, that validates the message's integrity. If the sender and receiver get different checksums, they will know that the message was corrupted at some point during the transmission of the message. Sometimes, errors in data transmission can occur, or an attacker might have maliciously altered the message. 

Another common use of cryptographic hashes is for password verification. When you create an account, you select a unique username and a password. Every time you sign in after that, you must put in your username and the correct password. This information must be stored by the service you are accessing, and a common way of storing this information is storing a hashed version of the password you selected. Every time you attempt to sign in, the password you typed in would be hashed again using the same algorithm, and then compared to the stored hashed password. You may wonder why your plaintext password isn't stored instead. If the list of usernames and passwords were stolen by an attacker, it would be too easy for them read all of the information and gain access to everyone's accounts. However, if the passwords were all hashed, it would make it much more difficult for the attacker to figure out everyone's passwords since hashes cannot be easily reversed to reveal the original message. It was previously mentioned that there are many people who have generated long lists of common passwords and their hash values, and these lists can easily be used to reveal a password from a hash. This is why it is important to create a strong password. If you picked a common password such as "password123" it is very likely on numerous lists of common passwords and their corresponding hashes, making it very easy for an attacker to discover your password if they gain unauthorized access to your stored password hash. 


## Password Salting
Now that you know that there are many lists of commonly used passwords, you may wonder what happens if two people pick the same password. It is definitely possible for two users with different usernames to pick the same password. Usually, when you create an account, the service checks whether or not the username you pick is already taken, but it does not check if your chosen password is already being used by another user. Thus, if you look at a very large list of everyone's usernames and password hashes, you may notice that there are multiple usernames that are associated with the same common password hash. If this list is very, very large, it is highly likely that the most common hash corresponds to the most commonly used password. There are many published lists of commonly used passwords and their likelihood to be used in a given year. [NordPass](https://nordpass.com/most-common-passwords-list/) has a list of common passwords, and you can even sort it by country. Although there is likely not a perfect correlation between number of occurrences  of a password and how generally common a password is, it would not take an attacker very long to figure out what the top passwords are. 

One way to help prevent the same hash from appearing in a stored list even when multiple users choose the same password is to use a technique called password salting. A salt is a random string of characters that is added to a user's password prior to hashing. Since the salt is always random, this would result in different password hashes even if multiple users choose the same password. Although the salt is a random string of letters, it is only generated randomly the first time when a user initially creates an account. After that, the salt information would be stored along with the username and hashed password, so that when the user signs in in the future, the salt would be added to the password, then hashed, and then compared with the stored value in the list. Adding a salt to every user's password not only helps prevent the same hashes from appearing multiple times, but also takes away the usefulness of the lists of common passwords and their hashes. 

# The Real World, Prolific Breaches
A good cryptographic hash function should never result in the same hash value from two different messages. To find weaknesses of the cryptographic hash algorithms, people attempt to find two input messages that would produce the same hash value. If this occurs, it is called a collision. The MD5 hash has been shown to have many collisions that are possible. With today's computing power, it is even possible to find collisions within seconds. About 20 years after the SHA-1 hash was introduced, a group of researches at Google and the CWI Institute in Amsterdam showed that they were able to provide two different PDF files that have different content but result in the same SHA-1 hash value. 

# Check YoSelf
## Q1 - True or False? If you have a hash, you can reverse it to obtain the original message. 
a. True <br>
b. False <---<br>

## Q2 - True or False? Cryptographic hashes are often used for password verification because is it not possible to store plaintext passwords. 
a. True <br>
b. False <---<br>

## Q3 - True or False? Password salting is used to prevent the same hash from appearing in a list of password hashes if multiple users have the same plaintext password. 
a. True <---<br>
b. False <br>

## Q4 - What is the purpose of a checksum?
a. Check a message for spelling errors. <br>
b. Verify that a message is not tampered with during message transmission. <---<br>
c. Verify the identity of the sender of a message. <br>
d. All of the above. <br>

# Keep Going, Next Steps
Check out the following curated resources if you'd like to keep learning about this topic to dominate hard challenges.
1. Details on Implementing Salted Password Hashing - https://crackstation.net/hashing-security.htm
2. Digital Signatures - https://www.ibm.com/docs/en/ztpf/1.1.0.14?topic=concepts-digital-signatures
3. MD5 Vulnerabilities - https://www.venafi.com/blog/patching-perpetual-md5-vulnerability
4. SHA-1 Collision - https://security.googleblog.com/2017/02/announcing-first-sha1-collision.html