# [MISC - Stegano]
## Watasi Wa...?
Do you know which universe this historical figure belongs to?

### Solution part 1/3:
We are presented with the image *Anime.jpg*. After inspecting the image in its hex representation and reading about .jpg file format we will see there is more in the file. So first thing let's cut out the first image until it's ending tag `FF D9`.  This is a 72123 bytes 400x350 image. One of the many tests to find interesting stegano stuff is to see if there are hidden pixels. To be quick we can use https://fotoforensics.com/ and in fact there are some. Let's change the image size in 400x400 so after the `FF C0` marker we change `01 5E 01 90` into `01 90 01 90`. By opening the image we get: `0K1TA-SAN`.

![first file](./images/anime1.jpg)

### Solution part 2/3:
Reopening the original and modified file we now see at the beginning 4 null-bytes which seem to be placeholders for **PKZIP** since the next bytes look much like a .zip file. So we replace them with `50 4B 03 04` and run `zip -FF Anime.jpg --out anime2.zip`. The zip's password isn't found in *rockyou.txt* nor in *crackstation.lst*. Removing the 242 bytes zip block we are left with a beginning 10 null bytes and trailing `FF D9`~~ISITDTU{Flag_N0t_h3re!!!}~~ . Assuming it's another jpg file, we replace the 10 bytes placeholder with `FF D8 FF E0 00 10 4A 46 49 46`. We get a working jpg file.

### Solution part 3/3:
In CTFs when you have a password and a JPEG, BMP, WAV or AU file, maybe `steghide` has been used. This check confirms it:
```bash
$ stegseek --seed anime3.jpg 
StegSeek 0.6 - https://github.com/RickdeJager/StegSeek

[i] Found (possible) seed: "811b8ba2"            
	Plain size: 35.0 Byte(s) (compressed)
	Encryption Algorithm: rijndael-128
	Encryption Mode:      cbc
```
Let's continue:
```bash
$ steghide extract -v --stegofile anime3.jpg --passphrase 0K1TA-SAN
reading stego file "anime3.jpg"... done
extracting data... done
checking crc32 checksum... ok
writing extracted data to "S3cr3t.txt"... done
$
$ cat S3cr3t.txt 
FG0!!!
$
$ 7z e -p'FG0!!!' anime2.zip 
7-Zip [64] 16.02 : Copyright (c) 1999-2016 Igor Pavlov : 2016-05-21
p7zip Version 16.02 (locale=en_US.UTF-8,Utf16=on,HugeFiles=on,64 bits,8 CPUs Intel(R) Core(TM) i5-10210U CPU @ 1.60GHz (806EC),ASM,AES-NI)
Scanning the drive for archives:
1 file, 242 bytes (1 KiB)
Extracting archive: anime2.zip
--
Path = anime2.zip
Type = zip
Physical Size = 242
Everything is Ok
Size:       24
Compressed: 242
$
$ cat flag.txt 
ISITDTU{St3g0_15_Fun!!!}
