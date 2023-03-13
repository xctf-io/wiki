---
title: Ciphers
---

## Substitution Ciphers

### What is a Substitution Cipher?

A Substitution cipher is a way of encrypting data, where every occurrence of specific letter from the alphabet within the plaintext you supply, is substituted by another character from the alphabet. This encrypted series of characters is given to the recipient, who knows what the character substitutions are and can reverse the process to get the plaintext back again.

For example:

```
A = X
B = D
C = H
D = S
... (and so on)
```

The key here is the arrangement of letters mapped to the original. If you possess the above key (in full) then returning the data to the original plaintext (decryption) is trivial - simply reverse it. There may be more complex substitution methods, for example, pairs of characters AB = MK rather than singles, but the above is a common and simple method.

You can also apply the same logic to bytes. If the same substitution is used throughout the message the cipher is referred to as monoalphabetic, whereas a polyalphabetic cipher uses a number of substitutions at different positions in the message.

### Breaking a Substitution Cipher

Breaking a substitution cipher is relatively easy, as long as you have a large enough sample of the ciphertext. The most common method is to use a frequency analysis of the ciphertext, and compare it to the frequency of letters in the English language. The most common letters in the English language are E, T, A, O, I, N, S, H, R, D, L, C, U, M, W, F, G, Y, P, B, V, K, J, X, Q, Z. If you have a large enough sample of the ciphertext, you can compare the frequency of letters in the ciphertext to the frequency of letters in the English language, and work out which letters are most likely to be which. For example, if you have a large sample of ciphertext, and the letter E is the most common, then you can assume that the most common letter in the plaintext is E. You can then work out the second most common letter, and so on.

Another method is to use a crib dragging attack. This is where you take a known plaintext, and drag it across the ciphertext, and compare the results. For example, if you know that the plaintext is "I love you", and you drag it across the ciphertext, you can see that the most common letters are "I", " ", "l", "o", "v", "e", "y", "u". You can then use this information to work out the most common letters in the ciphertext, and work out the key.

> These ciphers can be broken quite easily, so they are not used in real-world applications. 

## Caesar or ROT Cipher

### What is a Caesar Cipher?

The Caesar cipher is a substitution cipher where each letter in the plaintext is replaced by a letter a fixed number of positions down the alphabet. For example, if the shift is 3, then A becomes D, B becomes E, C becomes F, and so on. The shift is the number of positions down the alphabet that each letter is replaced by. The shift can be any number between 1 and 25, and is usually referred to as the key. It is named after Julius Caesar, who used it to communicate with his generals. It also has other names, including ROT (for "rotate") and shift cipher.

For example
```
offset = 13
T + 13 = G
E + 13 = R
S + 13 = F
T + 13 = G
I + 13 = V
N + 13 = A
G + 13 = T
```

### Breaking a Caesar Cipher

Because are only 26 possible keys, it is possible to brute force a Caesar cipher. This means that you can try every possible key, and see which one produces the most readable plaintext. This is a very simple method, and can be done by hand, or by a computer. The Caesar Cipher is not very secure, and is not used in real-world applications.

## Vigenere Cipher

### What is a Vigenere Cipher?

The Vigenere cipher is a substitution cipher that uses a series of Caesar ciphers based on the letters of a keyword. It is a form of polyalphabetic substitution. Each letter of the keyword is treated as a Caesar cipher with a shift value of its alphabetical position. Non-alphabetical characters are ignored. For example, if the keyword is "TRAIN", then the first letter, T, is shifted by 20 places, the second letter, R, by 18 places, and so on. Punctuation, spaces and numbers are left as is and are not encoded. This means that the key must be repeated for the length of the message, or be at least as long as the message. For example, if the message is "HELLO WORLD", and the key is "TRAIN", then the key would be repeated to form "TRAINTRAINT". The ciphertext would be "EIOZC ZRCEG".

### Breaking a Vigenere Cipher

The Vigenere cipher is much more secure than the Caesar cipher, but can still be broken by frequency analysis. Because the Vigenere cipher uses multiple Caesar ciphers, it is possible to break each one individually, and then work out the key. This is known as a Kasiski examination. This is a very complex method, and is not covered in here. However, there are a number of online tools that can do this for you. One such tool is [quipqiup](http://quipqiup.com/).

