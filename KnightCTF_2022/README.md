  
  
  
  
  
  
  
  
  
# OSINT  
## Canada Server (50)  
_Our sponsor NS TechValley had some problems last year. Their Canada server was not working as expected. Can you find the IP address of that server?_  
Flag Format : KCTF{IP_Address_Here}  
Example Flag : KCTF{127.0.0.1}  
Author : NomanProdhan  
###  
  
## Find The Camera (100)  
_Can you find the manufacturer and the model number of the camera that took the picture of this bus?_  
_Note: The whole flag is in Upper Case letters and replace any special character or space with underscores._  
Download Link(https://kctf2022.nstechvalley.com/knight-ctf-2022-challenges/OSINT/Find%20The%20Camera/)  
Flag Format: KCTF{MANUFACTURER_MODEL_SINGLELETTERNUMBER}  
Flag Example: KCTF{CANON_ABCD_A123}  
Author : marufmurtuza  
###  
  
# Cryptography  
## Passwd (25)  
_Find out the password of knight user._  
Download Link(https://kctf2022.nstechvalley.com/knight-ctf-2022-challenges/Cryptography/Password/passwd)  
Flag Format : KCTF{plain_text_password_here}  
Example Flag : KCTF{letmein}  
Author : 1xR1FAT  
###  
  
## 404 Not Found (25)  
_Something is wrong with this link. Is it really a link or someting else? Can you find out?_  
_Target Link: https://knightsquad.org/KCTF-2022?cypto=03MTJ3M2NjcfBDdfR2Mz42X1BTefN3MNFDdz0EMTtnRUN0S_  
  
__There is no need to do any fuzzing or bruteforcing. If you do so, your IP will be blocked for 24 hours.__  
__N:B: Only the provided link is in scope.__  
Flag Format : KCTF{plain_text_here}  
Example Flag : KCTF{flag}  
Author : 1xR1FAT  
###  
  
# Programming  
## Keep Calculating (25)  
_One of our clients needs a command line tool to do some math tasks. Can you create the tool by following pseudo code ?_  
- Let x = 1  
- Let y = 2  
- Let answer += (x * y) + xy [here xy = 12]  
- Repeat this calculation till you have x = 666  
- The final answer will be the flag when x = 666  
Flag Format : KCTF{answer_here}  
Example Flag : KCTF{123}  
Author : NomanProdhan  
###  
  
## Reverse The Answer (50)  
- Let x = 1  
- Let calculation = (x*(x+1)) + (2 *(x + 1))  
- Let reversed_calc = reversed number of calculation [for example if calculation = 123, reversed_calc will be 321]  
- If reversed_calc can be divided by 4 without reminder then answer = answer + reversed_calc  
- Repeat all the calculations until you have x = 543  
- The final answer will be the flag when x = 543  
Flag Format : KCTF{answer_here}  
Example Flag : KCTF{123}  
Author : NomanProdhan  
###  
  
## Square Sum (50)  
Have you ever heard the term "The sum of two squares"?  
It's like the following :  
4 = 0^2 + 2^2  
8 = 2^2 + 2^2  
16 = 0^2 + 4^2  
----------------------------  
5002 = 39^2 + 59^2 => 49^2 + 51^2 => 51^2 + 49^2 => 59^2 + 39^2  
And so on. In the example of 16, if we add the square of 0 & 4 we get 16. So here we are getting two values 0 & 4. So that's the answer.  
So write a program & find out the two values of 25000. Conditions are the following :  
- Remove the duplicates  
- Pick the third one  
Flag Format : KCTF{0,1}  
Author: TareqAhmed  
###  
  
## Something In Common (50)  
Find the GCD of the following numbers and add up the all integers of that GCD and multiply with 1234.  
Number 1: 21525625  
Number 2: 30135875  
Example: The GCD of 50 & 75 is 25.  
Here, 2 + 5 = 7  
So, the flag will be 7 x 1234 = 8638.  
Flag Format: KCTF{8638}  
Author: marufmurtuza  
###  
  
# Misc  
## Unzip Me (100)  
Can you unzip the file ?  
Download Link(https://kctf2022.nstechvalley.com/knight-ctf-2022-challenges/Misc/Unzip%20Me/unzipme.tar.gz)  
Flag Format: KCTF{S0m3_T3xt_H3re}  
Author: NomanProdhan  
###  
  
# Steganography  
## FileD (25)  
Can you see everything?  
Download Link(https://kctf2022.nstechvalley.com/knight-ctf-2022-challenges/Steganography/FileD/filed.kra)  
Flag Format: KCTF{S0m3_text_h3r3}  
Author: 1xR1fat  
###  
  
## Follow The White Rabbit (25)  
Will you choose to follow the white rabbit like NEO? THINK wisely or LOOK your path deeply before you take step.  
Download Link(https://kctf2022.nstechvalley.com/knight-ctf-2022-challenges/Steganography/Follow%20The%20White%20Rabbit/whiterabbit.jpg)  
Flag Format: KCTF{S0M3TEXTH3R3}  
Author: marufmurtuza  
###  
  
##  Follow (25)  
Follow the rules ?  
Download Links(https://kctf2022.nstechvalley.com/knight-ctf-2022-challenges/Steganography/Follow/Follow.pdf)  
Author: 1xR1fat  
###  
  
##  QR Code From The Future - (100)  
The following file was found in a device from a crashed UFO. Can you solve that mystery?  
Download Link(https://kctf2022.nstechvalley.com/knight-ctf-2022-challenges/Steganography/QR_Code_From_The_Future/QR_Code_From_The_Future.gif)  
Flag Example: KCTF{SOME_text_here}  
Author : marufmurtuza  
###  
  
## Bangladesh (100)  
My friend John was interested to know my country . He told me that to give him some images and articles about my county . I gave him some images and articles. In one image I provided some hidden data but he can not find hidden data . I told him Always remember 3 number sum equal to a game-changer. but he can not find hidden data . For that reason, I gave him that game-changer key.  
Download Link(https://kctf2022.nstechvalley.com/knight-ctf-2022-challenges/Steganography/Bangladesh/Bangladesh.jpg)  
###  
  
# Networking  
## Robots.txt (25)  
What is the file path in robots.txt?  
Use Compromised CTF Platform's Challenge file to analyze.  
Flag Format: KCTF{/path/path}  
Author : TareqAhamed  
###  
  
## Vuln (25)  
What vulnerability did the attacker exploited?  
Use Compromised CTF Platform's Challenge file to analyze.  
Flag Format: KCTF{vulnerability_name}  
Author : TareqAhamed  
###  
  
## FTP Flag (25)  
What is the ftp flag?  
Use Compromised CTF Platform's Challenge file to analyze.  
Flag Format: KCTF{Fl4g_H3r3}  
Author : TareqAhamed  
###  
  
## How's the Shark? (25)  
Find the flag from the following.  
Download Link(https://kctf2022.nstechvalley.com/knight-ctf-2022-challenges/Network/How's%20the%20Shark/data.pcapng)  
Flag Format: KCTF{ThE_FlAg_hEre}  
Author : TareqAhamed  
###  
  
## Find the Flag (50)  
Find the flag from the following file.  
Download Link(https://kctf2022.nstechvalley.com/knight-ctf-2022-challenges/Network/Find%20The%20Flag/file)  
Flag Format: KCTF{plain_t3xt_here}  
Author : TareqAhamed  
###  
  
## Compromised CTF Platform (50)  
I created a CTF platform of my own & hosted on a server. It seems like someone got access to my site. I have captured the traffic. Help me find out who he is.  
N.B: I am a n00b developer.  
What is the username & password that the attacker got.  
Download Link(https://kctf2022.nstechvalley.com/knight-ctf-2022-challenges/Network/Compromised%20CTF%20Platform/traffic.pcapng)  
Flag Format: KCTF{username_password}  
Author : TareqAhamed  
###  
  
## Vuln Columns (50)  
How many columns were vulnerable?  
Use Compromised CTF Platform's Challenge file to analyze.  
Flag Format: KCTF{0}  
Author : TareqAhamed  
###  
  
## Hashed Password (50)  
What is tareq's password hash?  
Use Compromised CTF Platform's Challenge file to analyze.  
Flag Format: KCTF{HASHEDPASSWORD}  
Author : TareqAhamed  
###  
  
## Admin Arena (50)  
What is the Admin Arena email id & password?  
Use Compromised CTF Platform's Challenge file to analyze.  
Flag Format: KCTF{email_password}  
Author : TareqAhamed  
###  
  
# Digital Forensics  
## The Lost Flag (25)  
We recovered a image file from an incident. There might be something interesting in the file. Give it a try.  
Download Link(https://kctf2022.nstechvalley.com/knight-ctf-2022-challenges/Digital%20Forensics/Lost%20Flag/Lost%20Flag%20.png)  
Flag Format: KCTF{pla1n_t3xt_here}  
Author : TareqAhamed  
###  
  
## Compromised FTP (25)  
We detected some malicious activity on our FTP server. Someone has performed bruteforce attack to gain access to our FTP server. Find out the Compromised FTP account username & the attacker IP from the following.  
Download Link(https://kctf2022.nstechvalley.com/knight-ctf-2022-challenges/Digital%20Forensics/Compromised%20FTP/ftp.log)  
Flag Format: KCTF{username_127.0.0.1}  
Author : TareqAhamed  
###  
  
## Unknown File (50)  
My friend sent me a file & told me there is a flag in it. He dare me to find the flag. But I have no idea what the file is about. Can you help me get the flag?  
Download Link(https://kctf2022.nstechvalley.com/knight-ctf-2022-challenges/Digital%20Forensics/Unknown%20File/unknown%20file.zip)  
Flag Format: KCTF{pla1n_t3xt_here}  
Author : TareqAhamed  
###  
  
## Let's Walk Together (50)  
Do you know anything about this image?  
Download Link(https://kctf2022.nstechvalley.com/knight-ctf-2022-challenges/Digital%20Forensics/Let's%20walk%20together/interesting_waves.png)  
Flag Format: KCTF{S0m3_Tex7_H3re}  
Author: TareqAhmed  
###  
  
