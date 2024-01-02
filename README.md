# Python_Mini-project

### This mini project contains 11 small assignments, which will help you get used to the fundamental concepts you've learned in the 1st week. They are divided into 2 parts:
- ***Compulsory: from 1 to 9***
- Optional: 10 and 11 (you can choose to do these questions or not)

### All of the tasks have examples of expected output for you to understand the requirements more easily. However, if there is anything ambiguous to you, do not hesitate to ask us.

### Good luck!


#### 1. Given a list of numbers. write a program to turn every item of a list into its square.

e.g:
- Input: [1, 2, 3, 4, 5, 6, 7]
- Expected output: [1, 4, 9, 16, 25, 36, 49]

```Python
list = [1, 2, 3, 4, 5, 6, 7]
squared_list = []

for i in list:
    squared_list.append(i**2)

print(squared_list)
```

[1, 4, 9, 16, 25, 36, 49]

---
#### 2. Display numbers which are both divisible by 3 and not divisible by 5 from a list.

e.g:
- Input: [10, 20, 33, 46, 54, 60]
- Expected output: 33, 54

```Python
list=[10, 20, 33, 46, 54, 60]
for i in list:
    if i%3==0 and i%5!=0:
        print(str(i)+" ", end = "")
    else:
        pass
```

33 54

---
#### 3. Convert two lists (with same size) into a dictionary

e.g:
- Input: keys = ['Ten', 'Twenty', 'Thirty']; values = [10, 20, 30]
- Expected output: {'Ten': 10, 'Twenty': 20, 'Thirty': 30}

```Python
keys = ['Ten', 'Twenty', 'Thirty']; values = [10, 20, 30]
dict=dict(zip(keys,values))
print(dict)
```

{'Ten': 10, 'Twenty': 20, 'Thirty': 30}

---
#### 4. Write a program to accept a string from the user and display characters that are present at an odd index number. For example, str = "unigap" so you should display 'n', 'g', 'p'.

```Python
str= "unigap"
odd_characters= []
for i in range(len(str)):
    if i%2!=0: odd_characters.append(str[i])
    else: pass
print(odd_characters)
```

['n', 'g', 'p']


---
#### 5. Reverse a given integer number
e.g:
- Given: 65869
- Expected: 96856

```Python
x=65869
rev=0

while(x>0):
    a=x%10
    rev=rev*10+a
    x=x//10

print(rev)
```

96856

---
#### 6. Calculate the sum of all numbers from 5 to a given number
- Write a program to accept a number from a user and calculate the sum of all numbers from 5 to a given number

For example, if the user entered 10 the output should be equal 5+6+7+8+9+10 = 45

```Python
def sum_from5(n):
    total=0
    for i in range(5,n+1):
        total +=i
    return total

# Example usage:
n = int(input("Enter a number: "))
result = sum_from5(n)
print(f"The sum of numbers from 5 to {n} is {result}")
```
Enter a number: 10
The sum of numbers from 5 to 10 is 45

---
#### 7. Calculate income tax for the given income by adhering to the below rules:
![1Capture](https://github.com/hatrang12/Python_Mini-project/assets/107136018/e502baa4-0117-4710-9034-854491b79e65)

For example, suppose the taxable income is 45000 the income tax payable is

10000x0% + 10000x10%  + 25000x20% = $6000.

```Python
def income_tax(i):
    if i<=10000:
        tax=i*0
    elif i<=20000:
        tax=(i-10000)*0.1
    else:
        tax=10000*0.1+(i-20000)*0.2
    return tax

i=30000
print(income_tax(i))
```

3000.0

---
#### 8. Convert a given tuple of integers into a new tuple which contains cube of each element of the original tuple. For example, if the original tuple is (1,2,3,4), the expected output is (1,8,27,64)

```Python
original_tuple = [1, 2, 3, 4]
cubed_tuple = []

for i in original_tuple:
    cubed_tuple.append(i**3)

print(cubed_tuple)
```

[1, 8, 27, 64]

---
#### 9. Determine the number of even, odd, and divisible by 3 in a list (using Def)
e.g:
- Input: list_num = [1,2,3,4,5,6,7]
- Expected output:
    - total even num is 3
    - total odd num is 4
    - total num divisible by 3 is 2

```Python
def count_even_odd_divisible_by_3(n):
    even_count=0
    odd_count=0
    divisible_by_3_count=0
    
    for i in list_num:
        if i%2==0:
            even_count+=1
        else:
            odd_count+=1
        
        if i%3 ==0:
            divisible_by_3_count +=1
    print(f"Total even numbers: {even_count}")
    print(f"Total odd numbers: {odd_count}")
    print(f"Total numbers divisible by 3: {divisible_by_3_count}")

list_num=[1,2,3,4,5,6,7]
count_even_odd_divisible_by_3(list_num)
```

Total even numbers: 3
Total odd numbers: 4
Total numbers divisible by 3: 2

---
#### 10. (optional) Given a sequence of characters to be considered a password. Check if the password is valid or not. A password is valid if and only if all of the following conditions are satisfied:


- At least 1 lowercase letter [a-z]
- At least 1 number [0-9]
- At least 1 uppercase letter [A-Z]
- At least 1 symbol in [$ @ #]
- Minimum password length: 6
- Maximum password length: 12

```Python
import re

def valid_password(password):
    #check length
    if 6<= len(password)<=12:
        #check for at least 1 lowercase letter
        if re.search(r'[a-z]', password):
            #check for at least 1 number
            if re.search(r'[0-9]', password):
                #check for at least 1 uppercase letter
                if re.search(r'[A-Z]', password):
                    #check for at least 1 symbol in [$@#]
                    if re.search(r'$@#', password):
                        return True
    return False

#Example usage:
password = input("Enter a password: ")
if valid_password(password):
    print("password is valid.")
else:
    print("password is not valid.")
```

Enter a password: Hatrang.98
password is not valid.

---
#### 11. (optional) Write a program that will be able to remove duplicates from a given array. The output should meet the following requirements:
- Sorted in ascending order
- Leading and trailing spaces removed
- Duplicates removed
- Each element's first character is uppercase.

#### For instance:
- Input: ["Panasonic ", " pensonic", "panasonic  ", " Haier", "electrolux","Electrolux"]
- Output: ['Electrolux', 'Haier', 'Panasonic', 'Pensonic']

```Python
def clean_array(input_array):
    #remove leading, trailing spaces, capitalize first character, and convert to set to remove duplicates
    cleaned_set = []
    for element in input_array: 
        cleaned_set.append(element.strip().capitalize())
    cleaned_set=set(cleaned_set)
    #sort the cleaned set in ascending order
    sorted_array = sorted(cleaned_set)
    
    return sorted_array

#example usage
input_array= ["Panasonic ", " pensonic", "panasonic ", " Haier", "electrolux","Electrolux"]
output_array= clean_array(input_array)

print("Input Array: ", input_array)
print("Output Array: ", output_array)
```

- Input Array:  ['Panasonic ', ' pensonic', 'panasonic ', ' Haier', 'electrolux', 'Electrolux']
- Output Array:  ['Electrolux', 'Haier', 'Panasonic', 'Pensonic']




