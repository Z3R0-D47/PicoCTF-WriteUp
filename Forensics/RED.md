# RED (Easy)

## Description 
RED, RED, RED, RED
Download the image: [red.png](https://challenge-files.picoctf.net/c_verbal_sleep/831307718b34193b288dde31e557484876fb84978b5818e2627e453a54aa9ba6/red.png)

- Hints
  - The picture seems pure, but is it though?
  - Red?Ged?Bed?Aed?
  - Check whatever Facebook is called now. (Meta=metadata)

Challenge Link: https://play.picoctf.org/practice/challenge/460

---

## Solution
### 1. Analyzing metadata of the PNG
We can use a tool called zsteg, which checks for hidden messages in image files, especially PNGs and BMPs.
```bash
zsteg -a red.png
```

Output
```bash
b1,rgba,lsb,xy      .. text: "cGljb0NURntyM2RfMXNfdGgzX3VsdDFtNHQzX2N1cjNfZjByXzU0ZG4zNTVffQ==cGljb0NURntyM2RfMXNfdGgzX3VsdDFtNHQzX2N1cjNfZjByXzU0ZG4zNTVffQ==cGljb0NURntyM2RfMXNfdGgzX3VsdDFtNHQzX2N1cjNfZjByXzU0ZG4zNTVffQ==cGljb0NURntyM2RfMXNfdGgzX3VsdDFtNHQzX2N1cjNfZjByXzU0ZG4zNTVffQ=="
```
Found a line of base64 encoded string. `cGljb0NURntyM2RfMXNfdGgzX3VsdDFtNHQzX2N1cjNfZjByXzU0ZG4zNTVffQ==`

### 2. Decode the base64 string
You can decode the string in the terminal.
```bash
echo "cGljb0NURntyM2RfMXNfdGgzX3VsdDFtNHQzX2N1cjNfZjByXzU0ZG4zNTVffQ==" | base64 -d
```

Output:
```bash
picoCTF{r3d_1s_th3_ult1m4t3_cur3_f0r_54dn355_} 
```

## Flag
```bash
picoCTF{r3d_1s_th3_ult1m4t3_cur3_f0r_54dn355_}
```

