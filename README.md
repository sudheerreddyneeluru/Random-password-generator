# Random-password-generator
# Contents
 Introduction:
 Outline:
 Project Prerequisites:
 Code Implementation:
 Source Code:
 Output:
 
# Introduction:
Let’s create a Random Password Generator that takes input as password length and generates a password of that length with the random characters.

The Random Password Generator is very useful when signing up for any website for temporary work and every time every user dont need to think about a new password. 
He can generate a password randomly and use it there for that moment. Did anyone think about creating our own program to build a Random Password Generator by ourselves?
and what if I tell you!! You can do the same thing with the help of a python script.

# Outline:
In this project, we will take password length as input from the user and generate a random string and give it as a result.
We just write our python script in any text editor or IDE and run it. After running the script and entering the password length, we will be given a random password of that length.

# Project Prerequisites:
You don’t have to install any package in your system to run this script. Because we just use this program to create a string with all the combinations of digits, characters, and special symbols.
The modules we use in this project are:
1. random
2. math
# random:
 This package provides a Python 3 ported version of Python 2.7’s random module. It has also been back-ported to work in Python 2.6.
In Python 3, the implementation of randrange() was changed, so that even with the same seed you get different sequences in Python 2 and 3.
 Note that several high-level functions such as randint() and choice() use randrange().
In my testing code, I heavily rely on stable random generator results and it makes porting code to Python 3 a lot harder if all those tests have to be adjusted. This package fixes that.
for more information about this library refer to this – [random2·PyPI]

# math:
Python has a built-in module that you can use for mathematical tasks.
The math module has a set of methods and constants.
for more information about this library refer to this – Python math Module (w3schools.com)

# Code Implementation:
The first thing we need to do is to import the required packages and modules. In this project, we import random and math modules to make use of their functions.
import random
import math
After the import section, we define three variables for storing alphabets, integers and special characters.
alpha = “abcdefghijklmnopqrstuvwxyz”
num = “0123456789”
special = “@#$%&*”
In this section of code implementation, we will define how much the length of the alphabets, integers and special characters must occupy in the resultant string.

# pass_len=random.randint(8,13)  #without User INput
pass_len = int(input(“Enter Password Length : “))
# length of password by 50-30-20 formula
alpha_len = pass_len//2 
num_len = math.ceil(pass_len*30/100)
special_len = pass_len-(alpha_len+num_len)
Now, we define an empty password list.
password = []
In this section, we define a function called generate_pass(), and we will append the respective alphabets, integers, or special characters based on the password length.

def generate_pass(length, array, is_alpha=False):

    for i in range(length):

        index = random.randint(0, len(array) – 1)

        character = array[index]

        if is_alpha:

            case = random.randint(0, 1)

            if case == 1:

                character = character.upper()

        password.append(character)

In the last section, we will call the generate_pass() function with all the possible ways of passing arguments and finally loop through the list and create the final string gen_password and print it.

# alpha password
generate_pass(alpha_len, alpha, True)
# numeric password
generate_pass(num_len, num)
# special Character password
generate_pass(special_len, special)
# suffle the generated password list
random.shuffle(password)
# convert List To string
gen_password = “”
for i in password:
    gen_password = gen_password + str(i)
print(gen_password)
the whole code is completed .

# output :
run the python script like the above-given command.
After running the source code, it will prompt to enter the password length then automaticaly system will generates ranndom password .


