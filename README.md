# Fitting Poisson  distribution
# Aim : 

To fit poisson distribution for the arrival of objects per minute from the feeder

# Software required :  

Python and Visual component tool

# Theory:

The Poisson distribution is the discrete probability distribution of the number of events occurring in a given time period, given the average number of times the event occurs over that time period.

![image](https://user-images.githubusercontent.com/104613195/166248326-fd042076-8b0b-40c4-8b11-1d8e8fcb74db.png)

 Conditions for Poisson Distribution:

1. An event can occur any number of times during a time period.
2. Events occur independently. I
3. The rate of occurrence is constant.
4. The probability of an event occurring is proportional to the length of the time period. 
 
# Procedure :

![image](https://user-images.githubusercontent.com/104613195/166251988-d0c53205-6080-4f7b-ae4c-398178586637.png)

# Program :
```
import math

# Observed frequencies
x = [0, 1, 2, 3, 4, 5]
f = [12, 20, 25, 18, 10, 5]

# Total frequency
N = sum(f)

# Mean (λ)
lam = sum(x[i] * f[i] for i in range(len(x))) / N

print("Mean (λ) =", round(lam, 4))

expected = []
chi_square = 0

print("\nX\tObserved\tExpected")

for xi, fi in zip(x, f):
    p = (math.exp(-lam) * (lam ** xi)) / math.factorial(xi)
    e = N * p
    expected.append(e)

    print(xi, "\t", fi, "\t\t", round(e, 2))

    chi_square += ((fi - e) ** 2) / e

print("\nChi-Square Value (χ²) =", round(chi_square, 4))
```
# Output : 
<img width="385" height="239" alt="image" src="https://github.com/user-attachments/assets/08e29382-76ec-48d0-935d-a2a43ea8f078" />

# Results
Thus To fit poisson distribution for the arrival of objects per minute from the feeder has executed corrctly.

The Poisson distribution is fitted for the objects arrived from feeder per minute and the data is tested using Chi-square test. 
 
