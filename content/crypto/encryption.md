---
title: Encryption
---

## Encryption v.s Encoding

Encryption and encoding are often confused. Encoding is a way to convert data from one format to another. For example, you can encode a string of text into a base64 string. Encoding is reversible, and is often used to make data more portable. Encoding is not secure, and should not be used to protect sensitive data. 

## XOR Encryption

The XOR cipher uses... you guessed it, the XOR (exclusive or). Much like other ciphers, you’ll have three components - the plaintext, the ciphertext and the key. One of the great properties of XOR is that if you have the 3 components, and you XOR any two, you can produce the other one. This somewhat naturally produces an encryption and decryption mechanism. This also provides reasonable security because if you have 1 of the 3 parts it is very hard to guess the other 2 correctly!

Let us look at an example by first reminding ourselves how XOR works:
```
0 XOR 0 = 0
0 XOR 1 = 1
1 XOR 0 = 1
1 XOR 1 = 0
```
This is the basis of the XOR cipher. The cipher works by taking the plaintext and XORing it with the key. This produces the ciphertext. To decrypt the ciphertext, you XOR it with the key again. This produces the plaintext again.

In this example, the plaintext is `HEY` and the key is `KEY`. When converting the plaintext and key to binary, we get the following:
```
HEY = 01001000 01000101 01011001
KEY = 01001011 01011001 01011001
```
Now we can XOR the plaintext with the key to get the ciphertext:
```
Ciphertext = 00000011 00011100 00000000
```

To do XOR encryption and decryption, you can use an online tool like [CyberChef](https://gchq.github.io/CyberChef/). With a small enough key, you can brute force the key and decrypt the ciphertext. However, with a large enough key, this becomes infeasible.

## Symmetric Encryption

This is a big topic! Encryption supports most modern applications and websites, as well as most of the technology around you. At this point in your study, we don't want to get too far in to encryption at the modern day working level, but let's cover some key concepts and show how you can encrypt and decrypt some data with strong encryption.

Symmetric encryption is where a key is used for both encryption and decryption. This same key can be used to encrypt and then decrypt. It is ideal in a scenario where I want to encrypt data, retain the key as a secret, and then decrypt later. Of course, I could also share it with another party via some out of bands mechanism to make sure the key is kept safe.

The most common symmetric encryption algorithm is AES. AES stands for Advanced Encryption Standard. It is a symmetric block cipher that can encrypt and decrypt data in blocks of 128 bits. AES is a very strong encryption algorithm, and is used in many applications. It is also used in the TLS protocol to encrypt data in transit.

[CyberChef](https://gchq.github.io/CyberChef/) has a great AES implementation. You can use it to encrypt and decrypt data. You can also encrypt and decrypt data using the `openssl` command line tool. You can use the following command to encrypt `coolfile.jpg` using AES-256-CBC:
```shell
$  openssl enc -aes256 -base64 -in coolfile.jpg -out coolfile.enc
enter aes-256-cbc encryption password:
Verifying - enter aes-256-cbc encryption password:
```
You can then decrypt the file using the following command:
```shell
$  openssl enc -d -aes256 -base64 -in coolfile.enc -out coolfile.jpg
enter aes-256-cbc decryption password:
```

## Asymmetric Encryption

Asymmetric encryption is where you have two keys - a public key and a private key. The public key can be shared with anyone, and the private key should be kept secret. The public key is used to encrypt data, and the private key is used to decrypt data. The private key is used to sign data, and the public key is used to verify the signature. This is a very common scenario in the real world. For example, you can use asymmetric encryption to encrypt data that only you can decrypt. You can also use asymmetric encryption to sign data, and then verify the signature using the public key.

The most common asymmetric encryption algorithm is RSA. RSA is a public key encryption algorithm. RSA is a very strong encryption algorithm, and is used in many applications. It is often used to encrypt data in transit, and to sign data.

RSA is a bit more complicated than AES, so we won't go into too much detail here. Reading the [Wikipedia article](https://en.wikipedia.org/wiki/RSA_(cryptosystem)) is a good place to start. 

