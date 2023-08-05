# Password-Generator
 ## This project automatically generates passwords based on user criteria and saves them in a text file for easy access and security.

#### Importing correct libraries

```
import random
import string
```
**import random** in Python allows you to utilize functions for  generating random numbers, selecting random elements, and shuffling sequences, adding randomness to your programs. On the other hand, import string provides access to constants and functions for working with strings, which can be useful for tasks like generating random passwords or manipulating strings in various ways.

#### Gathering User Input
```
print('Welcome to Password Generator:')

password = ''
numKey = int(input('How Many Characters Should the Password Be: '))
specKey = input('Should There Be Special Keys? (yes/no): ').lower()
```
The code above gathers the users requirements and stores the values in its appropriate variables.

```
if specKey == 'no' and numm == 'no':
    for i in range(numKey):
        password += random.choice(string.ascii_letters)
elif specKey == 'yes' and numm == 'yes':
    for i in range(numKey):
        password += random.choice(string.ascii_letters + string.digits + string.punctuation)
elif specKey == 'yes' and numm == 'no':
    for i in range(numKey):
        password += random.choice(string.ascii_letters + string.punctuation)
elif specKey == 'no' and numm == 'yes':
    for i in range(numKey):
        password += random.choice(string.ascii_letters + string.digits)

```
Depending on the values of specKey and numm, the program generates a random password that meets the specified criteria, adding characters from the appropriate sets (string.ascii_letters, string.digits, string.punctuation) in each iteration of the loop.

```
print(f'Your Password is:\n {password}')

dec = str(input('Would You Like To Save Your Password? (yes/no)')).lower()
usage = str(input('What Would You Like this Password Saved For?: '))

if dec == 'yes':
    savedPass = open('SavedPasswords.txt', 'a')
    savedPass.write('\n' + usage + '\t\t\t\t' + password)    
    savedPass.close()
```


In this code, after generating the password, it asks the user if they want to save it and what purpose it should be saved for. If the user decides to save the password (by entering 'yes'), the script will open the file 'SavedPasswords.txt' in append mode and write the usage and password details on a new line, separated by tabs. The file is then closed, storing the password and its corresponding usage for future reference.




