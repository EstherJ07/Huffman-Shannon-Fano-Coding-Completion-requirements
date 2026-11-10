# Huffman-Shannon-fano
# Aim:
Consider a discrete memoryless source with symbols and statistics {0.35, 0.2, 0.15, 0.12, 0.1, 0.08} for its output. 
Apply the Huffman and Shannon-Fano to this source. 
Show that by drawing the tree diagram, and 
Calculate the average code word length, entropy, variance, redundancy, and efficiency.
# Tools Required:
colab/jupyter

# Program:
# Huffman -
```
import numpy as np
import math

L = 0
hs = 0
p = []
lk = []

n = int(input("Enter the number of Samples : "))

for i in range(n):
    pr = float(input(f"Enter the probability of sample values {i + 1}: "))
    p.append(pr)

for j in range(n):
    l = float(input(f"Enter the length of the sample values {j + 1}: "))
    lk.append(l)

for k in range(n):
    Avg1 = p[k] * lk[k]
    L = L + Avg1

for k in range(n):
    e = p[k] * math.log(1 / p[k], 2)
    hs = hs + e

hs = round(hs, 3)
eff = round(hs / L, 3)
red = round(1 - eff, 3)

var = 0
for k in range(n):
    var1 = p[k] * (lk[k] - L) ** 2
    var = var + var1

var = round(var, 3)

print(f"Average Codeword Length is : {L}")
print(f"Entropy is : {hs}")
print(f"Efficiency is : {eff}")
print(f"Redundancy is : {red}")
print(f"Variance is : {var}")
```
Shannon-fano
```
import numpy as np
import math

L = 0
hs = 0
p = []
lk = []

n = int(input("Enter the number of Samples : "))

for i in range(n):
    pr = float(input(f"Enter the probability of sample values {i + 1}: "))
    p.append(pr)

for j in range(n):
    l = float(input(f"Enter the length of the sample values {j + 1}: "))
    lk.append(l)

for k in range(n):
    Avg1 = p[k] * lk[k]
    L = L + Avg1

for k in range(n):
    e = p[k] * math.log(1 / p[k], 2)
    hs = hs + e

hs = round(hs, 3)
eff = round(hs / L, 3)
red = round(1 - eff, 3)

var = 0
for k in range(n):
    var1 = p[k] * (lk[k] - L) ** 2
    var = var + var1

var = round(var, 3)

print(f"Average Codeword Length is : {L}")
print(f"Entropy is : {hs}")
print(f"Efficiency is : {eff}")
print(f"Redundancy is : {red}")
print(f"Variance is : {var}")
```
# Calculation:

<img width="800" height="900" alt="image" src="https://github.com/user-attachments/assets/ad3a9b66-bb7e-4ddb-8000-8123bf40b160" />

<img width="800" height="999" alt="image" src="https://github.com/user-attachments/assets/d2bf4745-bc4a-44a8-b241-79a7ffd3a97c" />

# Output
<img width="508" height="342" alt="image" src="https://github.com/user-attachments/assets/b32b3512-2304-4a6f-a466-f0b3fc11d5dc" />


# Results:
For the given discrete memoryless source with probabilities {0.35, 0.2, 0.15, 0.12, 0.1, 0.08} , both Huffman and Shannon–Fano coding were applied. The simulation was carried out in Python (Google Colab). Since the source probabilities are exact powers of two, the codeword lengths match the ideal values, giving zero redundancy and 100% coding efficiency. Both Huffman and Shannon–Fano yield identical results.
