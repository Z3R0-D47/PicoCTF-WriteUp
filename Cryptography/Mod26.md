# Mod 26(Easy)

## Description
Cryptography can be easy, do you know what ROT13 is? 
```bash
cvpbPGS{arkg_gvzr_V'yy_gel_2_ebhaqf_bs_ebg13_Ncualgvd}
```

- Hints
  - This can be solved online if you don't want to do it by hand!

Challenge Link: https://play.picoctf.org/practice/challenge/144

---

## Solution
### 1. Decode the `ROT13` string
Copy the string `cvpbPGS{arkg_gvzr_V'yy_gel_2_ebhaqf_bs_ebg13_Ncualgvd}` and decode using an online decoder:
- [CyberChef](https://gchq.github.io/CyberChef/)
- [dCode](https://www.dcode.fr/rot-13-cipher)
- [crytii](https://cryptii.com/)
  
These are a few online decoders that I recommend. Any of them will work.

```bash
picoCTF{next_time_I'll_try_2_rounds_of_rot13_Aphnytiq}
```
After copying the string and decode it using a `ROT13` decoder, we found the flag.

## Flag
```bash
picoCTF{next_time_I'll_try_2_rounds_of_rot13_Aphnytiq}
```
