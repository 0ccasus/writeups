## Misc

### Unzip Me (100)
Can you unzip the file ? [Download Link](./files/Unzip%20Me/unzipme.tar.gz)  
Flag Format: KCTF{S0m3_T3xt_H3re}  
Author: NomanProdhan  

After downloading we decompress through gzip the file. After we look at the contents of the newly created file. We will see that 2 bytes are swapped if compared to a regular zip file. I.e. it should begin `50 4b 03 04`.
```
$ tar -xvzf unzipme.tar.gz 
unzipme

$ xxd unzipme
00000000: 4b50 0403 0014 0000 0000 1de3 542c 7cfe  KP..........T,|.
00000010: 4750 001e 0000 001e 0000 0008 0000 6c66  GP............lf
00000020: 6761 742e 7478 434b 4654 737b 5f4f 4f79  gat.txCKFTs{_OOy
00000030: 5f75 5773 5061 3350 5f44 4874 5f65 3166  _uWsPa3P_DHt_e1f
00000040: 334c 0a7d 4b50 0201 033f 0014 0000 0000  3L.}KP...?......
00000050: 1de3 542c 7cfe 4750 001e 0000 001e 0000  ..T,|.GP........
00000060: 0008 0000 0000 0000 0000 0000 81a4 0000  ................
00000070: 0000 6c66 6761 742e 7478 4b50 0605 0000  ..lfgat.txKP....
00000080: 0000 0001 0001 0036 0000 0044 0000 0000  .......6...D....
```
Through Python we can achieve the desired result: swapping the bytes as they should be. Then we can unzip and read the flag.
```python
with open('unzipme', 'rb') as fh:
    data = fh.read()
    fixed = bytearray()
    for i in range(0, len(data), 2):
        fixed.append(data[i+1])
        fixed.append(data[i])

with open('unzipme.zip', 'wb') as fh:
    fh.write(fixed)
```
```bash
$ unzip unzipme.zip 
Archive:  unzipme.zip
 extracting: flag.txt
                 
$ cat flag.txt 
KCTF{sO_yOu_sWaPP3D_tHe_f1L3}
```