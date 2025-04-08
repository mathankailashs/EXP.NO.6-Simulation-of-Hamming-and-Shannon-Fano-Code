# HUFFMAN AND SHANNON_FANO
Consider a discrete memoryless source with symbols and statistics {0.125, 0.0625, 0.25, 0.0625, 0.125, 0.125, 0.25} for its output. Apply the Huffman and Shannon-Fano to this source.

## AIM:
To compute the Average Codeword Length, Entropy, Efficiency, Redundancy, and Variance for a discrete memoryless source using Huffman and Shannon-Fano coding based on the given probabilities and codeword lengths.

## TOOLS REQUIRED :
Python: A versatile language for scientific computing and signal processing. NumPy & Matplotlib: Libraries for numerical oper\Rations and high-quality visualizations, essential for demonstrating sampling.

## PROGRAM:
```
import numpy as np
import math 
L  = 0
hs = 0
p = []
lk = []
n = int(input("Enter the number of Samples : "))
for i in range (n): 
    pr = float(input(f"Enter the probability of sample values {i + 1}: "))  
    p.append(pr)
for j in range (n): 
    l = float(input(f"Enter the length of the sample values {j + 1}: "))  
    lk.append(l)

for k in range (n):
    Avg1 = p[k] * lk[k]
    L = L + Avg1

for k in range (n):
    e = p[k] * math.log(1 / p[k], 2)
    hs = hs + e
hs = round(hs,3)

eff = hs / L
eff = round(eff,3)

red =  round(1 - eff,3) 

var = 0
for k in range(n):
    var1 = p[k] * (lk[k]-L)**2
    var = var + var1
var = round(var,3)
print()
print(f"Average Codeword Length is : {L}")
print(f"Entropy is : {hs}")
print(f"Efficiency is : {eff*100} %")
print(f"Redudancy is : {red}")
print(f"Variance is : {var}")
```
## OUTPUT:
![image](https://github.com/user-attachments/assets/aac006a3-ccb0-408f-a962-a30a7fb7aafc)


## CALCULATIONS:
![430689041-cf9a5cf3-a8b3-4414-ac07-f140ae2801f1 MATHAN](https://github.com/user-attachments/assets/edd483f4-fdd6-4ab7-97dd-10204434fbfb)

![image](https://github.com/user-attachments/assets/2a6662d0-e366-4016-8ed1-bcf5c3a93a7a)
![image](https://github.com/user-attachments/assets/27994d70-0907-4e87-8cd3-2a577161fd1e)

## RESULT:
For the given probabilities 0.125,0.0625,0.25,0.0625,0.125,0.125,0.25. Average Codeword Length is : 2.625 Entropy is : 2.625 Efficiency is : 100.0 % Redudancy is : 0.0 Variance is : 0.484.
