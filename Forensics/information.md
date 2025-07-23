# information (Easy)

## Description
Files can always be changed in a secret way. Can you find the flag? [cat.jpg](https://mercury.picoctf.net/static/b4d62f6e431dc8e563309ea8c33a06b3/cat.jpg)

- Hints
  - Look at the details of the file
  - Make sure to submit the flag as picoCTF{XXXXX}

Challenge Link: https://play.picoctf.org/practice/challenge/186

---

## Solution
### 1. Check the metadata 
Check the metadata of cat.jpg using `exiftool cat.jpg`

```
Z3R0-D47-picoctf@webshell:~$ exiftool cat.jpg
ExifTool Version Number         : 12.40
File Name                       : cat.jpg
Directory                       : .
File Size                       : 858 KiB
File Modification Date/Time     : 2021:03:15 18:24:46+00:00
File Access Date/Time           : 2025:07:23 03:19:49+00:00
File Inode Change Date/Time     : 2025:07:23 03:19:49+00:00
File Permissions                : -rw-rw-r--
File Type                       : JPEG
File Type Extension             : jpg
MIME Type                       : image/jpeg
JFIF Version                    : 1.02
Resolution Unit                 : None
X Resolution                    : 1
Y Resolution                    : 1
Current IPTC Digest             : 7a78f3d9cfb1ce42ab5a3aa30573d617
Copyright Notice                : PicoCTF
Application Record Version      : 4
XMP Toolkit                     : Image::ExifTool 10.80
License                         : cGljb0NURnt0aGVfbTN0YWRhdGFfMXNfbW9kaWZpZWR9
Rights                          : PicoCTF
Image Width                     : 2560
Image Height                    : 1598
Encoding Process                : Baseline DCT, Huffman coding
Bits Per Sample                 : 8
Color Components                : 3
Y Cb Cr Sub Sampling            : YCbCr4:2:0 (2 2)
Image Size                      : 2560x1598
Megapixels                      : 4.1
```

A Base64-encoded string was discovered in the License metadata
```
cGljb0NURnt0aGVfbTN0YWRhdGFfMXNfbW9kaWZpZWR9
```

2. Decode the base64 string using [base64decode](https://www.base64decode.org/)
   <img width="1546" height="1090" alt="image" src="https://github.com/user-attachments/assets/1e7fcf2c-bbf1-41bd-a0a6-514a2672ae26" />

## Flag
```bash
picoCTF{the_m3tadata_1s_modified}
```
