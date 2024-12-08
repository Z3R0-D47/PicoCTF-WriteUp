# The Numbers(Easy)

## Description
The numbers... what do they mean?
```bash
16 9 3 15 3 20 6 { 20 8 5 14 21 13 2 5 18 19 13 1 19 15 14 }
```
<img width="387" alt="the_numbers" src="https://github.com/user-attachments/assets/38895362-2262-4ecd-ba0e-6752014b6f82">

- Hints
  - The flag is in the format PICOCTF{}
 
Challenge Link: https://play.picoctf.org/practice/challenge/68

---
## Solution
### 1. Decode the `Substitution Cipher(A1Z26)` string
Copy the string `16 9 3 15 3 20 6 { 20 8 5 14 21 13 2 5 18 19 13 1 19 15 14 }` and decode using an online decoder:
- [dCode](https://www.dcode.fr/letter-number-cipher)
```bash
PICOCTF{THENUMBERSMASON}
```
After copying the string and decode it using a `Substitution Cipher(A1Z26)` decoder, we found the flag.

## Explanation of Substitution Cipher(A1Z26)
The string `16 9 3 15 3 20 6 { 20 8 5 14 21 13 2 5 18 19 13 1 19 15 14 }` uses a ***Substitution Cipher***, specifically the ***A1Z26 cipher***. This cipher maps numbers to letters of the alphabet based on their position, where:

- 1 = A, 2 = B, ..., 26 = Z
1. Separate the Components:
The string can be broken into two parts:

- `16 9 3 15 3 20 6`
- `{ 20 8 5 14 21 13 2 5 18 19 13 1 19 15 14 }`
  
The first part appears to form the prefix, and the second part is enclosed in {}, which is typical for flags.

2. Map Numbers to Letters:
Convert each number to its corresponding letter using the A1Z26 cipher:

- `16 = P`, `9 = I`, `3 = C`, `15 = O`, `3 = C`, `20 = T`, `6 = F` → **PICOCTF**
- `20 = T`, `8 = H`, `5 = E`, `14 = N`, `21 = U`, `13 = M`, `2 = B`, `5 = E`, `18 = R`, `19 = S`, `13 = M`, `1 = A`, `19 = S`, `15 = O`, `14 = N` → **THENUMBERSMASON**
  
After that we can combine the Decoded Parts:

- Prefix: `PICOCTF`
- Suffix (inside {}): `THENUMBERSMASON`
  
Final result: **PICOCTF{THENUMBERSMASON}**

## Flag
```bash
PICOCTF{THENUMBERSMASON}
```




