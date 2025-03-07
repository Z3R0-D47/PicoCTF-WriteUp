# Interencdec (Easy)

## Description
Can you get the real meaning from this file?
Download the file [here](https://artifacts.picoctf.net/c_titan/3/enc_flag).

- Hints
  - Engaging in various decoding processes is of utmost importance.
 
Challenge Link: https://play.picoctf.org/practice/challenge/418
---

## Solution
### 1. Download and Inspect the File
Download the file using `wget`:

```bash
wget https://artifacts.picoctf.net/c_titan/3/enc_flag
```

After downloading, check its contents:

```bash
cat enc_flag
```

Output:

```
YidkM0JxZGtwQlRYdHFhR3g2YUhsZmF6TnFlVGwzWVROclgya3lNRFJvYTJvMmZRPT0nCg==
```

### 2. Decode the Base64 String
Since the string is Base64-encoded, decode it using:

```bash
echo "YidkM0JxZGtwQlRYdHFhR3g2YUhsZmF6TnFlVGwzWVROclgya3lNRFJvYTJvMmZRPT0nCg==" | base64 -d
```

Output:

```
b'd3BqdkpBTXtqaGx6aHlfazNqeTl3YTNrX2kyMDRoa2o2fQ=='
```

The result is another Base64-encoded string. The `b'...'` notation indicates it's a **byte string** from Python.

### 3. Decode the Second Base64 Layer
Remove the `b' '` and decode it again:

```bash
echo "d3BqdkpBTXtqaGx6aHlfazNqeTl3YTNrX2kyMDRoa2o2fQ==" | base64 -d
```

Output:

```
wpjvJAM{jhlzhy_k3jy9wa3k_i204hkj6}
```

This looks like a **Caesar cipher**-encrypted text.

### 4. Decrypt the Caesar Cipher
Using an **online Caesar cipher brute-force tool** like [dCode](https://www.dcode.fr/caesar-cipher), the plaintext is revealed as:

```
picoCTF{caesar_d3cr9pt3d_b204adc6}
```

### Why Multiple Base64 Layers?
Base64 encoding can be applied multiple times to obscure information. Each layer needs to be decoded separately to retrieve the original message. The final step used the **Caesar cipher**, which is a simple letter-shifting encryption method. You can learn more about caesaer cipher [here](https://www.geeksforgeeks.org/caesar-cipher-in-cryptography/).

---

## Flag
```bash
picoCTF{caesar_d3cr9pt3d_b204adc6}
```

