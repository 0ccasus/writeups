## Networking

### Robots.txt (25)  
What is the file path in robots.txt?  
Use Compromised CTF Platform's Challenge file to analyze.  
Flag Format: KCTF{/path/path}  
Author : TareqAhamed  

**wireshark** has definitely too many futures. One of them in ctf-context which is very useful is the `File > Export Objects > HTTP`. Object packet 343 shows the retrival of `robots.txt`. When marked and showing preview, we find the requested path.
```
User-agent: *
Disallow : /includes/users.php
```
Therefore the flag is `KCTF{/includes/users.php}`.  

---

### Vuln (25)  
What vulnerability did the attacker exploited?  
Use Compromised CTF Platform's Challenge file to analyze.  
Flag Format: KCTF{vulnerability_name}  
Author : TareqAhamed  

Looking around all the packets with **wireshark** we will soon notice that many sql injections have been tried. Also running **strings** and grepping for **sqlmap** (_the defacto tool for this kind of attacks_) we will see it. So the flag becomes `KCTF{sql_injection}`.

---

### FTP Flag (25)  
What is the ftp flag?  
Use Compromised CTF Platform's Challenge file to analyze.  
Flag Format: KCTF{Fl4g_H3r3}  
Author : TareqAhamed  

In **wireshark** we can use the `ftp-data` filter. After looking the packets, we will discover nr. 7317 represents the retrival of `flag.txt` through ftp. And contains a base64 encoded string:
```
$ echo S0NURntQNFNzVzByRF9TSDB1bERfQjNfU3RyMG5HX0VuMHVHaF9UMF9ndTNzU30= | base64 -d
KCTF{P4SsW0rD_SH0ulD_B3_Str0nG_En0uGh_T0_gu3sS}
```

---

### How's the Shark? (25)  
Find the flag from the following.  
[Download Link](./files/data.pcapng)  
Flag Format: KCTF{ThE_FlAg_hEre}  
Author : TareqAhamed  

Let's use the same technique as previously: `File > Export Objects > HTTP`. Selecting everything (_since there aren't so many objects/files_) and exporting in a directory. After looking all images, we discover the file `something%20something.png` representig the flag as: `KCTF{A_ShARk_iN_tHe_WirE}`.

---

### Find the Flag (50)  
Find the flag from the following file.  
[Download Link](./files/file)  
Flag Format: KCTF{plain_t3xt_here}  
Author : TareqAhamed  

Using `xxd file | head` we see what appears to be a **dumpcap** capture file. Unfortunately using **wireshark** doesn't help much since the content is too much messy. Although using **strings** we got a better visible output. In the hope there is somewhere the word flag, we can retrive part of this ftp session log file. After understanding what which best command to use, we get following:
```
$ strings file | grep -n -A 2 "for flag.txt"
4645:150 Opening BINARY mode data connection for flag.txt (57 bytes).
4646-S0NURntGVFBfUDRDSzNUX0M0cFR1cjNfVXNJbmdfV2lyZVNINFJLfQo=
4647-<;DB

$ echo S0NURntGVFBfUDRDSzNUX0M0cFR1cjNfVXNJbmdfV2lyZVNINFJLfQo= | base64 -d
KCTF{FTP_P4CK3T_C4pTur3_UsIng_WireSH4RK}
```
---
### Compromised CTF Platform (50)  
I created a CTF platform of my own & hosted on a server. It seems like someone got access to my site. I have captured the traffic. Help me find out who he is.  
N.B: I am a n00b developer.  
What is the username & password that the attacker got.  
[Download Link](./files/traffic.pcapng)  
Flag Format: KCTF{username_password}  
Author : TareqAhamed  

**wireshark** has really good filtering options, first. Second usually on login forms the POST method is used. Therefore we put a filter like `http.request.method == POST`. OSCP doesn't interest us. So 12 packets are left. With right-clicking and following the TCP streams we see various attempts (_5 in total_). One of them in which server response is good is user `demo` pass `demo` which is the wanted one. So the flag is `KCTF{demo_demo}`

---

### Vuln Columns (50)  
How many columns were vulnerable?  
Use Compromised CTF Platform's Challenge file to analyze.  
Flag Format: KCTF{0}  
Author : TareqAhamed  
  
Looking in **wireshark** at the _http object list_ and scrolling down, we can see the sqli attack as been done on `users.php?id=` only and began from packet 8171. I tried to understand many tutorials on how to recognise successfull attempts, unfortunately I didn't mange to find the answer the proper way. So I tried as solution ~~8~~, ~~6~~, `4`. So not the proper way and would be glad if someone could point me this step.

---

### Hashed Password (50)  
What is tareq's password hash?  
Use Compromised CTF Platform's Challenge file to analyze.  
Flag Format: KCTF{HASHEDPASSWORD}  
Author : TareqAhamed  

A try was to use `strings traffic.pcapng | grep -i tareq | grep -v facebook` and between the results we see: **3 TAREQ : $2Y$10$XVKEZO/NKM4KE073CPTEG.VKFTHMH1CCDPRDD5JWYWKFEZ6GZKZN.**  

---

### Admin Arena (50)  
What is the Admin Arena email id & password?  
Use Compromised CTF Platform's Challenge file to analyze.  
Flag Format: KCTF{email_password}  
Author : TareqAhamed  

A try was to use `strings traffic.pcapng | grep -i tareq | grep -v facebook` and between the results we see: **$email_id = "tareq@hackerzarena.com";
email=tareq%40hackerzarena.com&password=P%40%24%24w0Rd&submit=** which is: `P@$$w0Rd`  