# SWE_2021_41_2024_2_Week_6_Assignment


# Assignment 4


## Week 4: Example Code for Happy Number in Google Colab
[SWE_2021_41_2024_2_Week_4](https://github.com/Jandos07/SWE_2021_41_2024_2_week4)

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
5. Since the result is 1, we will consider it a **Happy number**

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
**Explanation**:
1. The isHappy() function returns True if the number is equal to 1, in which case it is happy
2. If the number is between 2 and 6, the function returns False, because it is not happy
3. If the number is greater than or equal to 7, it calculates the sum of the squares of the number's digits
4. The while function gets the last digit, squares it, then adds it to the sum
5. It then divides the number by 10 to repeat with the next digit until the number reaches 0
6. The function calls itself using the new sum to check if it is a happy number
7. The function returns True if one of the recursive iterations return True, ie. n == 1
8. The function returns False if one of the recursive iterations return False, ie. n != 1 and n <= 6

# Assignment 5
## Docker Container Commands Executed
---
Below are the commands that were executed within the `ub-cont` Docker container:

### 1. Start Docker Container
**Start docker container using:**
```bash
docker start ub-cont
```
This command lets the user enable their Docker container to start executing commands.
### 2. Check OS release information using:
```
docker exec ub-cont cat /etc/os-release
```
This command outputs the information on the operating system of the ub-cont container. The '/etc/os-release' file contains data about the operating system (name, version, etc.)

### Output:
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


### 3. Check Git Version
```
docker exec ub-cont git --version
```
This command checks the installed version of git in the Docker container.
### Output:
```
git version 2.43.0
```

### 4. Check Python Version:
```
docker exec ub-cont python3 --version
```
This command verifies the version of Python installed in the container.
### Output:
```
Python 3.12.3
```
### 5. Inspect Container Bindings:
```
docker inspect --format="{{ .HostConfig.Binds }}" ub-cont
```
This command outputs information on the bind mounts between the host machine and the Docker container. Bind mounts allow files or directories from the host to be mounted into a container.
### Output:
```
[C:\Users\jando\docker-stuff:/data]
```
## Additional Photos
There are some additional photos of the process of checking commands.
<div style="margin-bottom: 20px;">
    ![Screenshot 2024-10-13 221828](https://github.com/user-attachments/assets/636343c5-ed3a-4ed4-b10b-d70975865af5)
</div>
<div style="margin-bottom: 20px;">
    ![Screenshot 2024-10-13 222905](https://github.com/user-attachments/assets/64817c8c-321f-430e-a8ff-551744d6b7c3)
</div>
<div style="margin-bottom: 20px;">
    ![Screenshot 2024-10-13 223226](https://github.com/user-attachments/assets/b40319f9-d123-42a7-8941-f63ffdbe5e7d)
</div>
<div style="margin-bottom: 20px;">
    ![Screenshot 2024-10-13 223454](https://github.com/user-attachments/assets/c4c3ae13-bbad-432f-ae29-140cb9a44084)
</div>
<div style="margin-bottom: 20px;">
    ![Screenshot 2024-10-13 223753](https://github.com/user-attachments/assets/2dc3bec2-1001-4752-97ad-c7a93877185c)
</div>

