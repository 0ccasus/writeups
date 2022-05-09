## OSINT  
  
### Canada Server (50)  
Our sponsor NS TechValley had some problems last year. Their Canada server was not working as expected. Can you find the IP address of that server?  
Flag Format : KCTF{IP_Address_Here}  
Example Flag : KCTF{127.0.0.1}  
Author : NomanProdhan  

The first try was to `ping` the NS TechValley domain. Fortunately it worked.
```bash
$ ping nstechvalley.com
PING nstechvalley.com (192.99.167.83) 56(84) bytes of data.
64 bytes from vps-efa3d37a.vps.ovh.ca (192.99.167.83): icmp_seq=1 ttl=43 time=198 ms
^C
--- nstechvalley.com ping statistics ---
2 packets transmitted, 1 received, 50% packet loss, time 1002ms
rtt min/avg/max/mdev = 198.422/198.422/198.422/0.000 ms
```
That was the flag `KCTF{192.99.167.83}`.

---

### Find The Camera (100)  
Can you find the manufacturer and the model number of the camera that took the picture of this bus?  
Note: The whole flag is in Upper Case letters and replace any special character or space with underscores.  
![Download Link](./images/Bus.png)  
Flag Format: KCTF{MANUFACTURER_MODEL_SINGLELETTERNUMBER}  
Flag Example: KCTF{CANON_ABCD_A123}  
Author : marufmurtuza  

We get the picture of bus. Searching google for some keywords like `"jench012"`, `bus`, `photo`, `luxembourg` (_from the license plate_) we find https://fotobus.msk.ru/photo/267442/?vid=204172 and some info where also the used camera: `DSC-S980` which is a Sony Cybershot series model. And we get the flag `KCTF{SONY_DSC_S980}`.