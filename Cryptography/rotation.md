# rotation(Easy)

## Description
You will find the flag after decrypting this file

Download the encrypted flag here.
```bash
xqkwKBN{z0bib1wv_l3kzgxb3l_555957n3}
```

 - Hints
    - Sometimes rotation is right

Challenge Link: https://play.picoctf.org/practice/challenge/373

---
## Solution
### 1. Decode the `ROT` string
Copy the string:`xqkwKBN{z0bib1wv_l3kzgxb3l_555957n3}` and decode using an online decoder:

 - [dCode](https://www.dcode.fr/rot-cipher)


![image](https://github.com/user-attachments/assets/ca0f302e-a88c-4fc6-82d3-36503387c41c)

```bash
picoCTF{r0tat1on_d3crypt3d_555957f3}
```

After copying the string and decode it using a `ROT Cipher` decoder, we found the flag.


## ROT Cipher Explanation
A ROT cipher (rotation cipher) is a substitution cipher where each letter is replaced by another letter a fixed number of positions down the alphabet. For example:

 - ROT1 shifts letters by 1 (A → B, B → C, etc.).
 - ROT13 shifts by 13, reversing itself with another ROT13.

Numbers, symbols, and spaces are usually unchanged, depending on the implementation.

## Why Brute-Force?
ROT ciphers have only 25 possible keys, making them easy to crack with brute force by trying every shift until readable plaintext is found. This method is effective when the exact rotation is unknown, as in this challenge.

## Flag

```bash
picoCTF{r0tat1on_d3crypt3d_555957f3}
```
