
# My Python problem-solving portfolio
Problems are generated with Google Gemini<br>Answers are my own answers

## 2026/01/04 
## Question 
### The Challenge: Temperature Pivot Finder

Write a Python program that analyzes a list of daily temperatures to find a "Pivot Index." This is the position where the sum of all temperatures to the **left** of the index is exactly equal to the sum of all temperatures to the **right**.

**Requirements & Restrictions:**

**Requirements**

* Create an array (list) of integers representing temperatures, such as `temps = [10, -5, 3, 8, 2, 6]`.<br><br>
* Your logic must calculate the total sums on both sides for every possible index until a match is found.<br><br>
* If a pivot exists, print the index; if no such index exists, print `-1`.

**Restrictions**

* The solution must be contained within a `Main()` function that returns an empty string `""` while printing the result directly to the console.

---

## Result 
```py
def Main(List_Temps):
    List_Left = [] 
    List_Right = [] 
    Success=False; 
    Cur = 0;
    for x in range(0, len(List_Temps)-2):
        List_Left.clear() 
        List_Right.clear() 
        for y in range(0, x+1):
            List_Left.append(List_Temps[y])
        for z in range(x, len(List_Temps)):
            try:
                List_Right.append(List_Temps[z+2])
                Cur = y+1
            except:
                pass;
        if sum(List_Left)==sum(List_Right):
            print(Cur)
            Success= True; 
    if Success != True:
        print(-1)
    return "";

Main([10, -5, 3, 8, 2, 6]) 


```
####  Time Complexity --> O($n^2$)<br>Space Complexity --> O(n)






## Question 
### The Challenge: Array Equilibrium Point
You are tasked with finding all "peak elements" in a 1D integer array, where a peak is defined as an element that is strictly greater than its immediate neighbors. Create a Main() function that initializes an array of at least 10 random integers and iterates through it to identify these points. For elements at the boundaries (the first and last indices), they only need to be greater than their single neighbor to be considered a peak.

**Requirements & Restrictions:**

**Requirements**<br>
* You must print the index and the value of every peak found in the format: Index: [i], Value: [n].

**Restrictions** <br>
* You cannot use built-in Python functions like max(), sort(), or any external libraries like NumPy; you must use a standard list and a manual loop.

* Output: Your Main() function must return an empty string "", ensuring all results are displayed via print() calls.
## Result 
```py
import random; 
def Main():
    New_Array_Init = ['']*10;
    for x in range(0, len(New_Array_Init)):
        New_Array_Init[x] = random.randint(1, 100);
    New_Array_Init.insert(0, -100);
    New_Array_Init.append(-100)
    print(New_Array_Init)
    for y in range(1, len(New_Array_Init)-1):
        if (New_Array_Init[y] > New_Array_Init[y+1]) and ((New_Array_Init[y] > New_Array_Init[y-1])):
            print(f"Index: {y-1}, Value: {New_Array_Init[y]}")
    return "";

Main() 

```

####  Time Complexity --> O($n$)<br>Space Complexity --> O(n)
## Question 
### The Challenge: The Monotonic Trend Detector
You are tasked with writing a function to determine if a sequence of recorded data (like stock prices or sensor readings) follows a **Monotonic Trend**. A sequence is monotonic if it is either entirely non-increasing or entirely non-decreasing.

**Requirements & Restrictions:**




**Requirements:**

-   Create a list of 10 integers, for example: `data = [1, 2, 2, 3, 7]` (Monotonic) or `data = [1, 3, 2]` (Not Monotonic).
    
-   Your logic must check the entire array to see if the direction of change remains consistent (always $\geq$ or always $\leq$).
    
-   Print `True` if the array is monotonic and `False` if it is not.
    

**Restrictions:**

-   You must use a single manual loop to compare adjacent elements.
    
-   You cannot use `sort()`, `sorted()`, or any method that reorders the array.
    
-   Your `Main()` function must return `""` and print the result directly.
## Result 
```py
def Main(data):
    Monotonic_Up = True; ## Gaan groter en groter
    Monotonic_Down = True; ## Gaan kleiner en kleiner 
    
    for x in range(1, len(data)):
        if data[x] >= data[x-1]:
            pass;
        else:
            Monotonic_Up = False;
        if data[x] <= data[x-1]:
            pass;
        else:
            Monotonic_Down = False; 
    
    if Monotonic_Up and Monotonic_Down:
        print(True)
    else:
        print(False)
    return ""
    
Main([1, 1, 1, 1, 2, 3, 4, 5, 6])
    
```
####  Time Complexity --> O($n$)<br>Space Complexity --> O(1)
