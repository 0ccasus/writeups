## Programming

### Keep Calculating (25)  
One of our clients needs a command line tool to do some math tasks. Can you create the tool by following pseudo code ?  
  
- Let x = 1  
- Let y = 2  
- Let answer += (x * y) + xy [here xy = 12]  
- Repeat this calculation till you have x = 666  
- The final answer will be the flag when x = 666  

Flag Format : KCTF{answer_here}  
Example Flag : KCTF{123}  
Author : NomanProdhan  

The following script does the job:
```python
y, z = 2, 0
for x in range(1, 667):
    z += (x * y) + int(''.join(str(x) + str(y)))
print(f'KCTF{{{z}}}')
```
Which output is `KCTF{2666664}`.

---

### Reverse The Answer (50)  
- Let x = 1  
- Let calculation = (x*(x+1)) + (2 *(x + 1))  
- Let reversed_calc = reversed number of calculation [for example if calculation = 123, reversed_calc will be 321]  
- If reversed_calc can be divided by 4 without reminder then answer = answer + reversed_calc  
Repeat all the calculations until you have x = 543  
The final answer will be the flag when x = 543  

Flag Format : KCTF{answer_here}  
Example Flag : KCTF{123}  
Author : NomanProdhan  

```python
ans = 0
for x in range(1, 544):
    z = int(str((x*(x+1)) + (2 *(x + 1)))[::-1])
    if z % 4 == 0:
        ans += z
print(f'KCTF{{{ans}}}')
```  
Which output is `KCTF{12252696}`.

---
### Square Sum (50)  
Have you ever heard the term "The sum of two squares"?  
It's like the following :  
4 = 0^2 + 2^2  
8 = 2^2 + 2^2  
16 = 0^2 + 4^2  
  
5002 = 39^2 + 59^2 => 49^2 + 51^2 => 51^2 + 49^2 => 59^2 + 39^2  
And so on. In the example of 16, if we add the square of 0 & 4 we get 16. So here we are getting two values 0 & 4. So that's the answer. So write a program & find out the two values of 25000. Conditions are the following:    
- Remove the duplicates  
- Pick the third one  

Flag Format : KCTF{0,1}  
Author: TareqAhmed  

My solution for this: The square root of 25000 is 158.11388300841898. Therefore most probably there is not an a or b which is larger then 160. We find 6 combinations. Removing the 3 duplicates we are left with 3... and the third is: KCTF{90,130}
```python
c = []
for a in range(160):
    for b in range(160):
        if (a**2 + b**2) == 25000:
            c.append((a,b))
print(c)
print(f'KCTF{{{c[2][0]},{c[2][1]}}}')
```
---
### Something In Common (50)  
Find the GCD of the following numbers and add up the all integers of that GCD and multiply with 1234.  
- Number 1: 21525625  
- Number 2: 30135875  
- Example: The GCD of 50 & 75 is 25.  
- Here, 2 + 5 = 7  
- So, the flag will be 7 x 1234 = 8638.  

Flag Format: KCTF{8638}  
Author: marufmurtuza  

```python
from math import gcd

a, b, c = 21525625, 30135875, 0
for i in list(str(gcd(a,b))):
    c += int(i)
print(f'KCTF{{{c*1234}}}')
```
