# My Python problem-solving portfolio
Problems are generated with Google Gemini<br>
Answers are my own answers

## 2026/01/04 
## Question --> 
### The Challenge: Temperature Pivot Finder

Write a Python program that analyzes a list of daily temperatures to find a "Pivot Index." This is the position where the sum of all temperatures to the **left** of the index is exactly equal to the sum of all temperatures to the **right**.

**The Requirements**

* Create an array (list) of integers representing temperatures, such as `temps = [10, -5, 3, 8, 2, 6]`.
* Your logic must calculate the total sums on both sides for every possible index until a match is found.
* If a pivot exists, print the index; if no such index exists, print `-1`.

**The Restrictions**

* You **cannot** use the built-in `sum()` function; you must iterate through the array manually using loops.
* The solution must be contained within a `Main()` function that returns an empty string `""` while printing the result directly to the console.

---

Would you like me to provide a set of test cases to verify your code once you've finished?<br>
## Result --> 
```python
List_Temps = [10, -5, 3, 8, 2, 6]
List_Left = [] 
List_Right = [] 
Success=False; 
Cur = 0;
def Main():
    global List_Temps, List_Left, List_Right, Success; 
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

Main() 

```
