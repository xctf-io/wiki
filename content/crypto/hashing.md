---
title: Hashing
---

## What is Hashing?

Hashing is a super neat example of cryptography, with many important uses in data integrity. The algorithm used when hashing takes any input data (known as the plaintext) - such as a message, a file, a password - and produces a fixed size ciphertext; which is a hash value, most commonly referred to has a hash.

There are a few important properties that make up a strong algorithm:

Hashing algorithms should be one way, meaning it should not be possible to reverse the recipe to reproduce the original plaintext data. Additionally, the same input should always result in the same output - it is deterministic. This makes hashes a great way to store some sort of data that we don't need to decrypt, instead only using that hash value for validation needs at a future point in time.

For example, when a user registers at a site, the password provided is hashed and stored in a database. When the user returns in the future to login, the password they now provide will be also hashed using the same algorithm that originally produced the stored hash. The stored hash and this new hash are compared and if they match, the provided password must be correct! The plaintext is not (and should not ever!) be stored in the database. This gives safety in-case the database is ever breached, yet still allows for a safe & functioning login system.

In hashing algorithms, a small change in the plaintext data should result in significantly different output, reducing the likelihood an attacker is able to predict the outcome of the algorithm and in doing so, 'break' it. This is known as the avalanche effect.

Hashing algorithms should be collision reistant, meaning that it is difficult to produce two matching ciphertext for different pieces of plaintext data. A crytpographic hash is weaker and less useful if it is not unique to the plaintext provided.

Another common use is validating file contents. We can produce a hash value for a file and use this to validate whether a file has been modified since - if the file contents are different, the resulting hash will not match.

## Examples
Here's a couple of examples hashing the string `password123` in popular hashing algorithms; MD5 and SHA-1:
```shell
$ echo -n "password123" | md5sum
482c811da5d5b4bc6d497ffa98491e38

$ echo -n "password123" | shasum
cbfdac6008f9cab4083784cbd1874f76618d2a97
```

## Breaking Hashes

Hashing algorithms are designed to be one-way, meaning that it is not possible to reverse the recipe to reproduce the original plaintext data. However, there are some ways to 'break' a hash, and in doing so, find the original plaintext data. 

If the user chooses a weak password, such as `password123`, it is possible to use a dictionary attack to find the plaintext data. This is where a list of common passwords is used to try and match the hash value. If the hash matches, the password is found.

Brute force tools like [John the Ripper](https://www.openwall.com/john/) and [Hashcat](https://hashcat.net/hashcat/) can also be used to try and find the plaintext data. These tools can be used to try and find the plaintext data by trying every possible combination of characters, and comparing the hash value to the hash value of the plaintext data. If the hash matches, the password is found.