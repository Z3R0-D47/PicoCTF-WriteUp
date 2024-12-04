# Binary Search(Easy)
## Description
Want to play a game? As you use more of the shell, you might be interested in how they work! Binary search is a classic algorithm used to quickly find an item in a sorted list. Can you find the flag? You'll have ***1000*** possibilities and only ***10*** guesses.

Cyber security often has a huge amount of data to look through - from logs, vulnerability reports, and forensics. Practicing the fundamentals manually might help you in the future when you have to write your own tools!
You can download the challenge files here:
`challenge.zip`
```bash
ssh -p 59563 ctf-player@atlas.picoctf.net
```

Using the password `1ad5be0d`. Accept the fingerprint with `yes`, and ls once connected to begin. Remember, in a shell, passwords are hidden!

* Hint
   * Have you ever played hot or cold? Binary search is a bit like that.
   * You have a very limited number of guesses. Try larger jumps between numbers!
   * The program will randomly choose a new number each time you connect. You can always try again, but you should start your binary search over from the beginning - try around 500. Can you think of why?

Challenge Link: https://play.picoctf.org/practice/challenge/442

---

## Solution
After connecting using `ssh` and password `1ad5be0d` based on the instruction.

### 1. Using Binary Search to Guess the Number
Start with the middle of the range, ***500***. Adjust your guess based on the program’s feedback `(“Higher” or “Lower”)` until you find the correct number. 
```bash
Z3R0-D47-picoctf@webshell:~$ ssh -p 52747 ctf-player@atlas.picoctf.net
The authenticity of host '[atlas.picoctf.net]:52747 ([18.217.83.136]:52747)' can't be established.
ED25519 key fingerprint is SHA256:M8hXanE8l/Yzfs8iuxNsuFL4vCzCKEIlM/3hpO13tfQ.
This key is not known by any other names
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added '[atlas.picoctf.net]:52747' (ED25519) to the list of known hosts.
ctf-player@atlas.picoctf.net's password: 
Welcome to the Binary Search Game!
I'm thinking of a number between 1 and 1000.
Enter your guess: 500
Higher! Try again.
Enter your guess: 600
Higher! Try again.
Enter your guess: 700
Lower! Try again.
Enter your guess: 650
Lower! Try again.
Enter your guess: 630
Higher! Try again.
Enter your guess: 635
Higher! Try again.
Enter your guess: 640
Higher! Try again.
Enter your guess: 641
Higher! Try again.
Enter your guess: 642
Higher! Try again.
Enter your guess: 644
Congratulations! You guessed the correct number: 644
Here's your flag: picoCTF{g00d_gu355_3af33d18}
Connection to atlas.picoctf.net closed.
```
## Explanation and Logic Behind Binary Search
This challenge mimics the binary search algorithm, an efficient method for finding a target value in a sorted dataset by repeatedly halving the search range. The goal is to guess a number between ***1*** and ***1000*** within ***10*** attempts, leveraging binary search principles:

1. **Divide and Conquer**: Start at the midpoint of the range `(500)`.
2. **Feedback-Driven Adjustment**: Based on the program's response `("Higher" or "Lower")`, adjust your search to the upper or lower half.
3. **Repeat**: Continue halving the range and guessing the midpoint until you find the target.
This approach mimics the binary search's efficiency, reducing the number of guesses to a logarithmic scale. With ***1000*** possibilities, binary search ensures you find the correct number in at most ***10*** guesses, as `log2(1000)≈10`.

​
## Flag
```bash
picoCTF{g00d_gu355_3af33d18}
```

