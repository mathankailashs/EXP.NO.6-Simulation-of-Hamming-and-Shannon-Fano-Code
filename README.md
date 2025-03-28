# EXP.NO.6-Simulation-of-Hamming-and-Shannon-Fano-Code
6. Simulation of Hamming and Shannon-Fano Code
 Consider a discrete memoryless source with symbols and statistics {0.125, 0.0625, 0.25, 0.0625, 0.125, 0.125, 0.25} for its output. Apply the Huffman and Shannon-Fano to this source.

# AIM
To compute the Average Codeword Length, Entropy, Efficiency, Redundancy, and Variance for a discrete memoryless source using Huffman and Shannon-Fano coding based on the given probabilities and codeword lengths.

# SOFTWARE REQUIRED
Python: A versatile language for scientific computing and signal processing. NumPy & Matplotlib: Libraries for numerical operations and high-quality visualizations, essential for demonstrating sampling.

# ALGORITHMS
**Huffman Coding Procedure :**

Count Frequencies: Determine the occurrence of each symbol in the data.
Create Priority Queue: Build a min-heap of nodes, each representing a symbol and its frequency.
Merge Nodes: Repeatedly extract the two lowest frequency nodes, create a parent node with their combined frequency, and insert the parent back into the heap.
Build Tree: Continue merging until only the root of the Huffman tree remains.
Generate Codes: Traverse the tree, assigning '0' to left branches and '1' to right branches to obtain the Huffman code for each symbol.

**Shannon-Fano Coding Procedure :**

Count Frequencies: Determine the occurrence of each symbol in the data.
Sort by Frequency: Arrange the symbols in descending order of their frequencies.
Divide and Assign: Recursively divide the sorted list into two sublists with roughly equal total frequencies. Assign '0' to the codes of symbols in the first sublist and '1' to the second.
Recurse: Repeat the division and assignment process for each sublist until each sublist contains only one symbol.
Collect Codes: The resulting binary sequences for each symbol form the Shannon-Fano codes.

# PROGRAM
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



# OUTPUT
![image](https://github.com/user-attachments/assets/56085d10-0dad-4951-9a96-794cd86282c2)

**calculation:**
![image](https://github.com/user-attachments/assets/3fcb507d-97db-4ff8-8ce7-e52f1c509d78)
![image](https://github.com/user-attachments/assets/cfecf2b8-b25c-4a7b-9266-dc2392046c83)
![image](https://github.com/user-attachments/assets/f47d7076-c81c-4898-8336-f1f1cbcddc26)


 
# RESULT
For the given probabilities 0.125,0.0625,0.25,0.0625,0.125,0.125,0.25.
Average Codeword Length is : 2.625 
Entropy is : 2.625 
Efficiency is : 100.0 %
Variance is : 0.484.
