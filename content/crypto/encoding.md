---
title: Encoding
---

## ASCII

ASCII or the American Standard Code for Information Interchange is an encoding scheme designed to represent simple text characters on computers. When a computer stores (or transmits) data, it fundamentally does so in binary: a sequence of 1s and 0s (or high/low voltage on a wire). ASCII provides a means of mapping those binary values to characters we understand. It acts as a way to translate our preferred method to read and write information (letters, numbers, symbols etc) to the way a computer prefers (binary). This is primarily done via a "lookup table". 

For example, the ASCII character "A" is represented by the binary value 01000001. The ASCII character "B" is represented by the binary value 01000010. The ASCII character "C" is represented by the binary value 01000011. And so on. 

ASCII not only provides a way to represent the 26 letters of the English alphabet, but also numbers, punctuation, and other symbols. It also provides a way to represent "control characters" such as carriage return, line feed, and tab.

But what about other languages? What about emojis? What about other symbols? ASCII is limited in its ability to represent all of the characters we may want to use. In order to represent more characters, we need to use a different table, such as the [Unicode](https://en.wikipedia.org/wiki/Unicode) table. Unicode is a superset of ASCII, and includes all of the characters that ASCII can represent, plus many more.

## Hexadecimal

Hexadecimal (otherwise known as hex) is hugely important in computer science and cyber security, especially on offensive tasks, hacking and defensive roles like forensics. Typically, in everyday life we use a base 10 numbering system (aka Decimal), that is; numbers 0 - 9. Hexadecimal however is base 16 (think of "hex" being 6, like hexagon and "decimal" being 10, like decade ... 6 + 10 = 16). A base 16 system stores values in a more space efficient and easy to process way for computers. For example, 10 in decimal is reprsented by 1010 in binary and A in hexadecimal. 

Having data in hex format doesn't change the underlying data, it is just a more efficient way of communicating that data. For this reason it's often used as a means of encoding and sometimes computers will convert data to hexadecimal before transmitting it. A lot of web applications will do this, for example.

If you want to convert data to or from other formats quickly and easily, there's some great online tools available. Simply just search for what you'd like to achieve and there will be a range of great tools ready to covert data for you.

There's some great hex editing tools to make use of if you need to do more than just a quick conversion. [HxD](https://mh-nexus.de/en/hxd/) is a great free tool for Windows, and [Hex Fiend](https://ridiculousfish.com/hexfiend/) is a great free tool for Mac. If you want an online tool, [HexEdit](https://hexed.it/) is a great option.

### Base64 and Base32

Base64 is a common encoding scheme for converting complex data to a simple text based format. Like any encoding scheme, it can be both encoded and then decoded back to the original data, but in its encoded form can be easier to store or transfer, especially in more restrictive scenarios where only text is feasible to use.

One example may be an embedded image in an email; you shouldn't store the binary data of the image file in the email file (typically .eml or .msg format) as the email file format needs to contain just text contents only. In this case you'd encode the image file as Base64, so it's in simple text only format and that's then fine to store in an email file.

Another example may be when you've gained access to a server and need to extract a file but transfer means such as SCP aren't available. Copying & pasting file contents may be a quick solution, but if you display binary data, copy that and paste it to a new file on your local machine, it very likely won't result in a working file as not all machine-readable data is displayable and so some data will be lost in transfer.

Instead, the contents can be displayed in Base64 encoding, copied and pasted into a new file on your local machine and finally decoded back to the original binary format. This is much less likely to fail as during transfer (copying & pasting to your clipboard) as you are dealing with just simple text (Base64 contents), avoiding the original problem.

Base64 and Base32 are not encryption. They're not meant to obfuscate or obscure data from a potential reader, they simply transform data into a different format for storage or transfer. There are many websites, command line tools and code modules which facilitate conversion to and from Base64. For example, on the Linux command line, you can use the base64 command to encode data quickly as follows:

```shell
$ echo "How are you today?" | base64
SG93IGFyZSB5b3UgdG9kYXk/Cg==
```
As you can see in the example above, a common way of spotting Base64 encoded data is trailing `=` characters at the end (there may be 0 - 2 of these!). This is because part of encoding the original data is to split data into 24 bit chunks, and if the chunk is shorter than 24 bits the data is 'padded' to fill in the gap, possibly resulting in the '=' characters you see - they're "filler". Another indication is if it contains alphanumeric characters (plus `+` or `/` characters) as mentioned previously.