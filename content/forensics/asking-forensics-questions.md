# Asking Forensics Questions

So you are looking at some piece of **evidence**. **Evidence** could be anything from a website, to an image, to even simply a piece of text. With forensics, it is all about asking the right questions and looking for the answers. For example, lets take a look at this piece of text:

> aGFoYSB5b3UgZm91bmQgbWUh

Looks pretty weird right? If you didn't know what you were looking at, it can be pretty confusing. Luckily, there are tools that exist that can help us get some ideas quickly. [CyberChef](https://gchq.github.io/CyberChef/#recipe=To_Base64('A-Za-z0-9%2B/%3D')&input=aGFoYSB5b3UgZm91bmQgbWUh) is a great tool and in this case helps us out! We can drag and drop different filters to discover that this text was encoded with [Base64](https://en.wikipedia.org/wiki/Base64).

> haha you found me!

## Text
- Are there patterns to the characters that I am looking at?
	- [Common text encoding formats](https://en.wikipedia.org/wiki/Binary-to-text_encoding)

## Image
- What metadata exists on the image?
	- Author
	- GPS Coordinates
- Is there any content hidden inside of the image as text?
- Can I do a [reverse image search](https://images.google.com/) to find the original image?
- Could there be [[what-is-steganography|steganography]] hidden in the image?

## Website
- 