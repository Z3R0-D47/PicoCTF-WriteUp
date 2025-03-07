# Hide and Seek (Easy)

## Description
How about some hide and seek?
Download this file [here](https://artifacts.picoctf.net/c_titan/6/unknown.zip).

- Hints
  - How can you view the information about the picture?
  - If something isn't in the expected form, maybe it deserves attention?
 
Challenge Link: https://play.picoctf.org/practice/challenge/408

---

## Solution
### 1. Extract the ZIP file
Download and unzip the file:

```bash
unzip unknown.zip
  inflating: ukn_reality.jpg 
```

This extracts an image file named `ukn_reality.jpg`.

### 2. Check Image Metadata
Use `exiftool` to inspect the metadata:

```bash
Z3R0-D47-picoctf@webshell:~$ exiftool ukn_reality.jpg 
ExifTool Version Number         : 12.40
File Name                       : ukn_reality.jpg
Directory                       : .
File Size                       : 2.2 MiB
File Modification Date/Time     : 2024:02:15 22:40:21+00:00
File Access Date/Time           : 2024:02:15 22:40:21+00:00
File Inode Change Date/Time     : 2025:03:06 16:13:34+00:00
File Permissions                : -rw-r--r--
File Type                       : JPEG
File Type Extension             : jpg
MIME Type                       : image/jpeg
JFIF Version                    : 1.01
Resolution Unit                 : inches
X Resolution                    : 72
Y Resolution                    : 72
XMP Toolkit                     : Image::ExifTool 11.88
Attribution URL                 : cGljb0NURntNRTc0RDQ3QV9ISUREM05fYTZkZjhkYjh9Cg==
Image Width                     : 4308
Image Height                    : 2875
Encoding Process                : Baseline DCT, Huffman coding
Bits Per Sample                 : 8
Color Components                : 3
Y Cb Cr Sub Sampling            : YCbCr4:2:0 (2 2)
Image Size                      : 4308x2875
Megapixels                      : 12.4
```

The output reveals a hidden Base64-encoded string in the **Attribution URL** field:

```
cGljb0NURntNRTc0RDQ3QV9ISUREM05fYTZkZjhkYjh9Cg==
```

### 3. Decode the Base64 String
Decode the string using the `base64` command:

```bash
echo "cGljb0NURntNRTc0RDQ3QV9ISUREM05fYTZkZjhkYjh9Cg==" | base64 -d
```

Output:

```bash
picoCTF{ME74D47A_HIDD3N_a6df8db8}
```

### Why Base64?
Base64 encoding is commonly used to encode binary data as text, making it easier to store and transmit. It often ends with  `=` or `==` as padding to ensure the encoded output is a multiple of 4 characters. Here, the flag was hidden in the metadata to obfuscate it.
You can also copy the string `cGljb0NURntNRTc0RDQ3QV9ISUREM05fYTZkZjhkYjh9Cg==` and decode using an online decoder:
- [CyberChef](https://gchq.github.io/CyberChef/)
- [dCode](https://www.dcode.fr/rot-13-cipher)
- [crytii](https://cryptii.com/)
  
These are a few online decoders that I recommend. Any of them will work.

---

## Flag
```bash
picoCTF{ME74D47A_HIDD3N_a6df8db8}
```

