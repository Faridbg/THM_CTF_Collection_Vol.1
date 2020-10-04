## CTF Collection Vol .1

---

#### [Task 2] What does the base said?

Can you decode the following? 

VEhNe2p1NTdfZDNjMGQzXzdoM19iNDUzfQ==

**Solution:**

~~~bash
$ echo VEhNe2p1NTdfZDNjMGQzXzdoM19iNDUzfQ== > data.txt
$ base64 -d data.txt 
THM{ju57_d3c0d3_7h3_b453}
~~~

---

#### [Task 3] Meta meta

Meta! meta! meta! meta...................................

Findme.jpg

**Solution:**

~~~bash
$ exif Findme.jpg
EXIF tags in 'Findme.jpg' ('Motorola' byte order):
--------------------+----------------------------------------------------------
Tag                 |Value
--------------------+----------------------------------------------------------
Resolution Unit     |Inch
YCbCr Positioning   |Centered
X-Resolution        |72
Y-Resolution        |72
Exif Version        |Unknown Exif Version
Components Configura|Y Cb Cr -
FlashPixVersion     |FlashPix Version 1.0
Camera Owner Name   |THM{3x1f_0r_3x17}
Color Space         |Uncalibrated
--------------------+----------------------------------------------------------

~~~

---

#### [Task 4] Mon, are we going to be okay?

Something is hiding. That's all you need to know.

Extinction.jpg

**Solution:**

~~~bash
$ steghide extract -sf Extinction.jpg -xf sol.txt 
Enter passphrase: 
wrote extracted data to "sol.txt".
$ cat sol.txt 
It going to be over soon. Sleep my child.

THM{500n3r_0r_l473r_17_15_0ur_7urn}
~~~

---

#### [Task 5] Erm......Magick

Huh, where is the flag? *THM{wh173_fl46}*

**Solution:**

THM{wh173_fl46}

---

#### [Task 6] QRrrrr

Such technology is quite reliable.

QR.png

**Solution:**

Scanning the QR results in: THM{qr_m4k3_l1f3_345y}

---

#### [Task 8] Another decoding stuff

Can you decode it?

3agrSy1CewF9v8ukcSkPSYm3oKUoByUpKG4L

**Solution:**

base58 decoder from CyberChef

THM{17_h45_l3553r_l3773r5}

---

#### [Task 9] Left or right

Left, right, left, right... Rot 13 is too mainstream. Solve this

MAF{atbe_max_vtxltk}

**Solution:**

rot7 decoder from CyberChef

THM{hail_the_caesar}

---

#### [Task 10] Make a comment

No downloadable file, no ciphered or encoded text. Huh .......

**Solution:**

On the html source code, inside a comment flag

 THM{4lw4y5_ch3ck_7h3_c0m3mn7}

---

#### [Task 11] Can you fix it?

I accidentally messed up with this PNG file. Can you help me fix it? Thanks, ^^

spoil.png

**Solution:**

~~~bash
$ hexedit spoil.png 
00000000   89 50 4E 47  0D 0A 1A 0A  00 00 00 0D  49 48 44 52  00 00 03 20  00 00 03 20  08 06 00 00  .PNG........IHDR... ... ....
~~~

Changing the first 4 hex values to the .PNG magic number and the viewing the image

THM{y35_w3_c4n}

---

#### [Task 12] Read it

Some hidden flag inside Tryhackme social account.

**Solution:**

Searching a post inside Tryhackme reddit

THM{50c14l_4cc0un7_15_p4r7_0f_051n7}

---

#### [Task 13] Spin my head

What is this?

++++++++++[>+>+++>+++++++>++++++++++<<<<-]>>>++++++++++++++.------------.+++++.>+++++++++++++++++++++++.<<++++++++++++++++++.>>-------------------.---------.++++++++++++++.++++++++++++.<++++++++++++++++++.+++++++++.<+++.+.>----.>++++.

**Solution:**

Brainfuck code. Decode with brainfuck decoder

THM{0h_my_h34d}

---

#### [Task 14] An exclusive!

Exclusive strings for everyone!

S1: 44585d6b2368737c65252166234f20626d
S2: 1010101010101010101010101010101010

**Solution:**

XOR calculation (<https://toolslick.com/math/bitwise/xor-calculator>).

The output is reversed, so:

~~~bash
$ echo }r0_3v15ulcx3{MHT | rev
THM{3xclu51v3_0r}
~~~

---

#### [Task 15] Binary walk

Please exfiltrate my file :)

hell.jpg

**Solution:**

~~~bash
$ binwalk -e hell.jpg 

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
0             0x0             JPEG image data, JFIF standard 1.02
30            0x1E            TIFF image data, big-endian, offset of first image directory: 8
265845        0x40E75         Zip archive data, at least v2.0 to extract, uncompressed size: 69, name: hello_there.txt
266099        0x40F73         End of Zip archive, footer length: 22

$ ls
Extinction.jpg  Findme.jpg  hell.jpg  _hell.jpg.extracted  hello.hello  QR.png  report.txt  spoil.png
$ cd _hell.jpg.extracted/
$ ls
40E75.zip  hello_there.txt
$ cat hello_there.txt 
Thank you for extracting me, you are the best!

THM{y0u_w4lk_m3_0u7}
~~~

---

#### [Task 16] Darkness

There is something lurking in the dark.

dark.png

**Solution:**

The solution inside the image, in a hidden layer. Using Image Steganography (<https://incoherency.co.uk/image-steganography/#unhide>)

THM{7h3r3_15_h0p3_1n_7h3_d4rkn355}

---

#### [Task 17] A sounding QR

How good is your listening skill?

P/S: The flag formatted as THM{Listened Flag}, the flag should be in All CAPS

**Solution:**

Scanning QR code and listening the file .

THM{SOUNDINGGQR}

---

#### [Task 18] Dig up the past

Sometimes we need a 'machine' to dig the past

Targetted website: https://www.embeddedhacker.com/
Targetted time: 2 January 2020

**Solution:**

Using Wayback Machine

 THM{ch3ck_th3_h4ckb4ck}

---

#### [Task 19] Uncrackable!

Can you solve the following? By the way, I lost the key. Sorry >.<

MYKAHODTQ{RVG_YVGGK_FAL_WXF}

Flag format: TRYHACKME{FLAG IN ALL CAP}

**Solution:**

Using brute force vigenere decoder 

TRYHACKME{YOU_FOUND_THE_KEY}

---

#### [Task 20] Small bases

Decode the following text.

581695969015253365094191591547859387620042736036246486373595515576333693

**Solution:**

Using brute force vigenere decoder 

TRYHACKME{YOU_FOUND_THE_KEY}

---

#### [Task 21] Read the packet

I just hacked my neighbor's WiFi and try to capture some packet. He must be up to no good. Help me find it.

flag.pcapng (Wireshark file)

**Solution:**

Using Wireshark, filtering by http. In the GET petition.

THM{d0_n07_574lk_m3}
