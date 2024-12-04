# Scan Surprise(Easy)
## Description
I've gotten bored of handing out flags as text. Wouldn't it be cool if they were an image instead?
You can download the challenge files here:
`challenge.zip`
The same files are accessible via SSH here:
```bash
ssh -p 58967 ctf-player@atlas.picoctf.net
```
Using the password `1db87a14`. Accept the fingerprint with `yes`, and `ls` once connected to begin. Remember, in a shell, passwords are hidden!

* Hint
  * QR codes are a way of encoding data. While they're most known for storing URLs, they can store other things too.
  * Mobile phones have included native QR code scanners in their cameras since version 8 (Oreo) and iOS 11
  * If you don't have access to a phone, you can also use `zbar-tools` to convert an image to text

Challenge Link: https://play.picoctf.org/practice/challenge/444

---
## Tool: zbar-tools
zbar-tools is a package for scanning and decoding barcodes and QR codes from images or live inputs.For this challenge, we use `zbarimg`, a tool designed to scan and decode barcodes or QR codes from image files.

Usage:
```bash
zbarimg <image>
```

## Solution
After connecting using `ssh` and password `1db87a14` based on the instruction.

### 1. Listing Files 
List the files in the directory using `ls` command.

```bash
ctf-player@challenge:~/drop-in$ ls
flag.png
```

### 2. Use `zbar-tools` to decode the qrcode
Use `zbarimg` from the `zbar-tools` to decode the image:

```bash
ctf-player@challenge:~/drop-in$ zbarimg flag.png
Connection Error (Failed to connect to socket /var/run/dbus/system_bus_socket: No such file or directory)
Connection Null
QR-Code:picoCTF{p33k_@_b00_19eccd10}
scanned 1 barcode symbols from 1 images in 0 seconds
```
The `Connection Error message` is unrelated and can be ignored. The tool successfully extracts the QR code content.


## Flag
```bash
picoCTF{p33k_@_b00_19eccd10}
```

