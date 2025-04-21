# Substitution0 (Medium)

## Description
A message has come in but it seems to be all scrambled. Luckily it seems to have the key at the beginning. Can you crack this substitution cipher?

```bash
DECKFMYIQJRWTZPXGNABUSOLVH 

Ifnfuxpz Wfyndzk dnpaf, oqbi d yndsf dzk abdbfwv dqn, dzk enpuyib tf bif effbwf
mnpt d ywdaa cdaf qz oiqci qb oda fzcwpafk. Qb oda d efdubqmuw acdndedfua, dzk, db
bidb bqtf, uzrzpoz bp zdbundwqaba—pm cpunaf d ynfdb xnqhf qz d acqfzbqmqc xpqzb
pm sqfo. Bifnf ofnf bop npuzk ewdcr axpba zfdn pzf flbnftqbv pm bif edcr, dzk d
wpzy pzf zfdn bif pbifn. Bif acdwfa ofnf flcffkqzywv idnk dzk ywpaav, oqbi dww bif
dxxfdndzcf pm eunzqaifk ypwk. Bif ofqyib pm bif qzafcb oda sfnv nftdnrdewf, dzk,
bdrqzy dww biqzya qzbp cpzaqkfndbqpz, Q cpuwk idnkwv ewdtf Juxqbfn mpn iqa pxqzqpz
nfaxfcbqzy qb.

Bif mwdy qa: xqcpCBM{5UE5717U710Z_3S0WU710Z_59533D2F}
```

- Hint  
    - Try a frequency attack. An online tool might help.

Challenge Link: https://play.picoctf.org/practice/challenge/307

---

## Solution

### 1. Observe the encrypted message
The ciphered message begins with a 26-character string that looks like a substitution key:
```bash
DECKFMYIQJRWTZPXGNABUSOLVH
```
This is likely a custom alphabet used to replace each letter in the standard alphabet (A–Z).
Since each letter is mapped consistently using a single substitution alphabet, this is most likely a monoalphabetic substitution cipher.


### 2. Why Monoalphabetic Substitution Cipher?
In this type of cipher:

- Each letter in the original alphabet (A–Z) is substituted with only one fixed letter from a cipher alphabet.
  
- The word "mono" means one-to-one mapping, meaning the substitution stays consistent throughout the entire message.

So, for this case, if the cipher key is:

```bash
Plain:   ABCDEFGHIJKLMNOPQRSTUVWXYZ
Cipher:  DECKFMYIQJRWTZPXGNABUSOLVH
```
Then the substitutions are always through the whole process:
- A → D
- B → E
- C → C
- D → K

...and so on.

This mapping doesn’t change at any point, which is what makes it mono-alphabetic (as opposed to polyalphabetic, where substitutions can vary based on position or key).

### 3. Decrypt the mono-alphabetic substitution cipher using online tool. 
We used [dode Mono-Alphabetic Substitution Decoder](https://www.dcode.fr/monoalphabetic-substitution). 
Paste the substitution key ```DECKFMYIQJRWTZPXGNABUSOLVH``` into the ***Knowing the substitution alphabet*** section, then paste the ciphertext into the main box.
![image](https://github.com/user-attachments/assets/87c95107-fadd-4222-8134-7df495c028c2)

## Flag
```bash
picoCTF{5UB5717U710N_3V0LU710N_59533A2E}
```

