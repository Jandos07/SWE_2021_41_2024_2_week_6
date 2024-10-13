# SWE_2021_41_2024_2_Week_6_Assignment

<br>
>> Assignment 4
<br>


## Week 4: Example Code for Happy Number in Google Colab
For Week 4, the main purpose was to write example code in **Google Colab** to check if a number is a **happy number**. I implemented the function and tested it with various cases.


### Problem Statement: Determine if a Number is Happy
A **happy number** is defined by the following process:
1. Starting with any positive integer, replace the number by the sum of the squares of its digits.
2. Repeat the process until the number equals 1 (where it will stay), or it loops endlessly in a cycle that does not include 1.
3. A number is considered happy if it eventually reaches 1.

### Example Problem
**Input**: 19  
**Output**: True (Happy number)

**Explanation**:
1. If we input 19 ,the calculation is: (1^2+9^2=1+81\)
2. Next, we apply the same method to 82:   (8^2 + 2^2 = 64 + 4 = 68\)
3. Next, 68: (6^2 + 8^2 = 36 + 64 = 100\)
4. Next, 100: (1^2 + 0^2 + 0^2 = 1 + 0 + 0 = 1\)
5. Since the result is 1, we wil consider it a (Happy number)

### Week 4 Code: Happy Number Function
The following Python code checks if a number is a happy number using a different approach:

```python
def isHappy(n):
    if n == 1:
        return True
     elif n <= 6:
        return False
    
    sum = 0
    while n > 0:
        digit = n % 10
        sum += digit ** 2
        n = n // 10
        
    return isHappy(sum)

# Input from the user
n = int(input("Enter a number: "))
print(isHappy(n))
