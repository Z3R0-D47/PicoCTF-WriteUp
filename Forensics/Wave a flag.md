# Wave a flag (Easy)

## Description
Can you invoke help flags for a tool or binary? This program has extraordinarily helpful information...

- Hints
  - This program will only work in the webshell or another Linux computer.
  - To get the file accessible in your shell, enter the following in the Terminal prompt: $ wget https://mercury.picoctf.net/static/fc1d77192c544314efece5dd309092e3/warm
  - Run this program by entering the following in the Terminal prompt: $ ./warm, but you'll first have to make it executable with $ chmod +x warm
  - -h and --help are the most common arguments to give to programs to get more information from them!
  - Not every program implements help features like -h and --help.

Challenge Link: https://play.picoctf.org/practice/challenge/170

---

## Solution
### 1. Make it executable and use -h argument
After download the file make it executable and use -h argument to get more information 
```bash
chmod +x warm
./warm -h
```

<img width="1160" height="80" alt="image" src="https://github.com/user-attachments/assets/4a64eb97-8464-42a8-9e2e-830dac4d5f55" />


## Flag
```bash
picoCTF{b1scu1ts_4nd_gr4vy_6635aa47}
```
