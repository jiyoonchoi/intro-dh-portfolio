---
layout: page
title: Exercises Ch. 5
description: If Statements
---

# Chapter 5: If Statements #

Course: Intro to Digital Humanities (CLS-161)

Section: Fall 2022

Creator: Jiyoon Choi

### 5-1. Conditional Tests: Write a series of conditional tests. Print a statement describing each test and your prediction for the results of each test. ###

- Look closely at your results, and make sure you understand why each line evaluates to True or False.
- Create at least ten tests. Have at least five tests evaluate to True and another five tests evaluate to False.


```python
flower = 'hibiscus'

# string comparison tests
print("Test 1: Is flower == 'hibiscus'? I predict True.")
print(flower == 'hibiscus')

print("\nTest 2: Is flower == 'chrysanthemum'? I predict False.")
print(flower == 'chrysanthemum')

# len comparison tests
print("\nTest 3: Is flower length == 8? I predict True.")
print(len(flower) == 8)

print("\nTest 4: Is flower length == 10? I predict False.")
print(len(flower) == 10)

# char comparison tests
print("\nTest 5: Is the first character of flower == 'h'? I predict True.")
print(flower[0] == 'h')

print("\nTest 6: Is the first character of flower == 'c'? I predict False.")
print(flower[0] == 'c')

print("\nTest 7: Is the last character of flower == 'h'? I predict True.")
print(flower[-1] == 's')

print("\nTest 8: Is the last character of flower == 'c'? I predict False.")
print(flower[-1] == 'm')

# type comparison tests
print("\nTest 9: Is the type of flower == str? I predict True.")
print(type(flower) == str)

print("\nTest 10: Is the type of flower == int? I predict False.")
print(type(flower) == int)
```

    Test 1: Is flower == 'hibiscus'? I predict True.
    True
    
    Test 2: Is flower == 'chrysanthemum'? I predict False.
    False
    
    Test 3: Is flower length == 8? I predict True.
    True
    
    Test 4: Is flower length == 10? I predict False.
    False
    
    Test 5: Is the first character of flower == 'h'? I predict True.
    True
    
    Test 6: Is the first character of flower == 'c'? I predict False.
    False
    
    Test 7: Is the last character of flower == 'h'? I predict True.
    True
    
    Test 8: Is the last character of flower == 'c'? I predict False.
    False
    
    Test 9: Is the type of flower == str? I predict True.
    True
    
    Test 10: Is the type of flower == int? I predict False.
    False


### 5-2. More Conditional Tests: You don’t have to limit the number of tests you create to ten. If you want to try more comparisons, write more tests and add them to conditional_tests.py. Have at least one True and one False result for each of the following: ###

- Tests for equality and inequality with strings
- Tests using the lower() method
- Numerical tests involving equality and inequality, greater than and less than, greater than or equal to, and less than or equal to
- Tests using the and keyword and the or keyword
- Test whether an item is in a list
- Test whether an item is not in a list


```python
print("Are the strings 'dog' and 'cat' equal?")
print('dog' == 'cat')

print("\nAre the lowered versions of 'Classics' and 'classics' equal?")
print('Classics'.lower() == 'classics'.lower())

print("\nIs 42 / 6 greater than 4?")
print(42 / 6 > 4)

print("\nIs 3 less than 5 or greater than 7")
print(3 < 5 or 3 > 7)

print("\nIs 3 less than 5 and greater than 7")
print(3 < 5 and 3 > 7)

stuff = ['foo', 'blah']
print(f"\nChecking items in list: {stuff}.")
print("\nIs 'foo' in the list?")
print('foo' in stuff)
print("\nIs 'foop' in the list?")
print('foop' in stuff)
```

    Are the strings 'dog' and 'cat' equal?
    False
    
    Are the lowered versions of 'Classics' and 'classics' equal?
    True
    
    Is 42 / 6 greater than 4?
    True
    
    Is 3 less than 5 or greater than 7
    True
    
    Is 3 less than 5 and greater than 7
    False
    
    Checking items in list: ['foo', 'blah'].
    
    Is 'foo' in the list?
    True
    
    Is 'foop' in the list?
    False


### 5-6. Stages of Life: Write an if-elif-else chain that determines a person’s stage of life. Set a value for the variable age, and then: ###

- If the person is less than 2 years old, print a message that the person is a baby.
- If the person is at least 2 years old but less than 4, print a message that the person is a toddler.
- If the person is at least 4 years old but less than 13, print a message that the person is a kid.
- If the person is at least 13 years old but less than 20, print a message that the person is a teenager.
- If the person is at least 20 years old but less than 65, print a message that the person is an adult.
- If the person is age 65 or older, print a message that the person is an elder.


```python
age = 19
if age < 2:
    print("The person is a baby.")
elif age >= 2 and age < 4:
    print("The person is a toddler.")
elif age >= 4 and age < 13:
    print("The person is a kid.")
elif age >= 13 and age < 20:
    print("The person is a teenager.")
elif age >= 20 and age < 65:
    print("The person is an adult.")
elif age >= 65:
    print("The person is an elder.")
```

    The person is a teenager.


### 5-7. Favorite Fruit: Make a list of your favorite fruits, and then write a series of independent if statements that check for certain fruits in your list. ###

- Make a list of your three favorite fruits and call it favorite_fruits.
- Write five if statements. Each should check whether a certain kind of fruit is in your list. If the fruit is in your list, the if block should print a statement, such as You really like bananas!


```python
favorite_fruits = ['mango', 'banana', 'plum']
if 'mango' in favorite_fruits:
    print("You love mangoes!")
if 'banana' in favorite_fruits:
    print("You love bananas!")
if 'plum' in favorite_fruits:
    print("You love plums!")
if 'apple' in favorite_fruits:
    print("You love apples!")
else: print("You may like apples, but you don't love them!")
if 'papaya' in favorite_fruits:
    print("You love papayas!")
else: print("You may like papayas, but you don't love them!")
```

    You love mangoes!
    You love bananas!
    You love plums!
    You may like apples, but you don't love them!
    You may like papayas, but you don't love them!


### 5-8. Hello Admin: Make a list of five or more usernames, including the name 'admin'. Imagine you are writing code that will print a greeting to each user after they log in to a website. Loop through the list, and print a greeting to each user: ###

- If the username is 'admin', print a special greeting, such as Hello admin, would you like to see a status report?
- Otherwise, print a generic greeting, such as Hello Jaden, thank you for logging in again.



```python
users = ['admin', 'jiyoon', 'jeana', 'seensook', 'jun']
for user in users:
    if user == 'admin':
        print("Hello admin, would you like to see a status report?")
    else: print(f"Hello {user.title()}, thank you for logging in again.")
```

    Hello admin, would you like to see a status report?
    Hello Jiyoon, thank you for logging in again.
    Hello Jeana, thank you for logging in again.
    Hello Seensook, thank you for logging in again.
    Hello Jun, thank you for logging in again.


### 5-9. No Users: Add an if test to hello_admin.py to make sure the list of users is not empty. ###

If the list is empty, print the message We need to find some users!
Remove all of the usernames from your list, and make sure the correct message is printed.


```python
users.clear()

if len(users) == 0:
    print("We need to find some users!")
```

    We need to find some users!


### 5-10. Checking Usernames: Do the following to create a program that simulates how websites ensure that everyone has a unique username. ###

- Make a list of five or more usernames called current_users.
- Make another list of five usernames called new_users. Make sure one or two of the new usernames are also in the current_users list.
- Loop through the new_users list to see if each new username has already been used. If it has, print a message that the person will need to enter a new username. If a username has not been used, print a message saying that the username is available.
- Make sure your comparison is case insensitive. If 'John' has been used, 'JOHN' should not be accepted. (To do this, you’ll need to make a copy of current_users containing the lowercase versions of all existing users.)


```python
current_users = ['Joy', 'Gail', 'Amanda', 'Pooja', 'Zoe']
lower_current_users = []

for user in current_users:
    lower_current_users.append(user.lower())

new_users = ['StepHanie', 'POOJA', 'eVa', 'Ashna', 'joy']

for user in new_users:
    if user.lower() in lower_current_users:
        print(f"The username '{user.title()}' is already taken. Please enter a new username.")
    else: print(f"The username '{user.title()}' is available.")
```

    The username 'Stephanie' is available.
    The username 'Pooja' is already taken. Please enter a new username.
    The username 'Eva' is available.
    The username 'Ashna' is available.
    The username 'Joy' is already taken. Please enter a new username.

