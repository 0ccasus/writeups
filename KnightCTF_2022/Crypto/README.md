## Cryptography  
  
### Passwd (25)  
Find out the password of knight user.  
[Download Link](./files/passwd)  
Flag Format : KCTF{plain_text_password_here}  
Example Flag : KCTF{letmein}  
Author : 1xR1FAT  
  
This is a Linux-type password file. `$ cat passwd | grep knight | cut -d ":" -f 3 | hash-identifier` shows that most probably MD5 is the algorithm used. The first quick try is taking immediate advantage of [CrackStation](https://crackstation.net/) or similar in order to discover that it is the encrypted `exploit` string.  

---  

### 404 Not Found (25)  
Something is wrong with this link. Is it really a link or someting else? Can you find out?  
Target Link: https://knightsquad.org/KCTF-2022?cypto=03MTJ3M2NjcfBDdfR2Mz42X1BTefN3MNFDdz0EMTtnRUN0S  
_There is no need to do any fuzzing or bruteforcing. If you do so, your IP will be blocked for 24 hours._  
N:B: Only the provided link is in scope.  
Flag Format : KCTF{plain_text_here}  
Example Flag : KCTF{flag}  
Author : 1xR1FAT  

The first try here was to see if it's base64 encoded. But it wasn't in the immediate. After solving some other challenges, I noticed the last part of the string beeing `S0NUR...`, which was the beginning of other base64 encoded flags. So let's decode

```python
from base64 import b64decode

print(b64decode('=03MTJ3M2NjcfBDdfR2Mz42X1BTefN3MNFDdz0EMTtnRUN0S'[::-1]))
```
... and we get **KCTF{S0M3t1M3s_y0u_n33d_t0_r3v3rS3}**.