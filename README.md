# SWE_2021_41_2024_2_Week_6_Assignment


# Assignment 4


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
```
# Assignment 5
## Docker Container Commands Executed
---
Below are the commands that were executed within the `ub-cont` Docker container:

### 1. Start Docker Container
**Start docker container using:**
```bash
docker start ub-cont
```
![Screenshot 2024-10-13 221828](https://github.com/user-attachments/assets/09c9efc1-48c9-4574-ab66-5cea5a972d3f)

docker exec ub-cont cat /etc/os-release

docker exec ub-cont git --version

Output:
```
PRETTY_NAME="Ubuntu 24.04.1 LTS"
NAME="Ubuntu"
VERSION_ID="24.04"
VERSION="24.04.1 LTS (Noble Numbat)"
VERSION_CODENAME=noble
ID=ubuntu
ID_LIKE=debian
HOME_URL="https://www.ubuntu.com/"
SUPPORT_URL="https://help.ubuntu.com/"
BUG_REPORT_URL="https://bugs.launchpad.net/ubuntu/"
PRIVACY_POLICY_URL="https://www.ubuntu.com/legal/terms-and-policies/privacy-policy"
UBUNTU_CODENAME=noble
LOGO=ubuntu-logo
```
![Screenshot 2024-10-13 222905](https://github.com/user-attachments/assets/fdc0fabd-a2ef-4ec6-949f-85b71b71e1d9)

3.Chech Git Version
docker exec ub-cont git --version
Output:
git version 2.43.0
![Screenshot 2024-10-13 223226](https://github.com/user-attachments/assets/160f1bee-71bd-42b9-be64-c8dd5587845a)

4.Chech Python Version:
docker exec ub-cont python3 --version
Output:
Python 3.12.3
![Screenshot 2024-10-13 223454](https://github.com/user-attachments/assets/87731d33-5218-422e-bc0d-29929ee9a24e)
5.Inspect Container Bindings:
docker inspect --format="{{ .HostConfig.Binds }}" ub-cont
Output:
![Screenshot 2024-10-13 223753](https://github.com/user-attachments/assets/2266bd75-a6cd-4e06-aef3-c1623386766c)
