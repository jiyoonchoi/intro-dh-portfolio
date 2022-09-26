---
layout: page
title: Exercises Ch. 2
description: Completed exercises from Python Crash Course
---

# Chapter 2: Variables and Simple Data Types

Course: Intro to Digital Humanities (CLS-161)

Section: Fall 2022

Creator: Jiyoon Choi

### 2-1. Simple Message: Store a message in a variable, and then print that message. ###


```python
dog = "I love dogs!"
print(dog)
```

    I love dogs!


### 2-2. Simple Messages: Store a message in a variable, and print that message. Then change the value of your variable to a new message, and print the new message. ###


```python
cat = "I also love cats!"
print(cat)
cat = "I do not love cats."
print(cat)
```

    I also love cats!
    I do not love cats.


### 2-3. Personal Message: Store a person’s name in a variable, and print a message to that person. Your message should be simple, such as, “Hello Eric, would you like to learn some Python today?” ###


```python
name = "Bob Belcher"
message = f"Hello {name}, what's on the menu today?"
print(message)
```

    Hello Bob Belcher, what's on the menu today?


### 2-4. Name Cases: Store a person’s name in a variable, and then print that person’s name in lowercase, uppercase, and titlecase. ###


```python
name = "Tina Belcher"
print(name.lower())
print(name.upper())
print(name.title())
```

    tina belcher
    TINA BELCHER
    Tina Belcher


### 2-5. Famous Quote: Find a quote from a famous person you admire. Print the quote and the name of its author. Your output should look something like the following, including the quotation marks: ###

*Albert Einstein once said, “A person who never made a mistake never tried anything new.”*


```python
print(f"Mahatma Gandhi once said, \"Be the change that you wish to see in the world.\"")
```

    Mahatma Gandhi once said, "Be the change that you wish to see in the world."


### 2-6. Famous Quote 2: Repeat Exercise 2-5, but this time store the famous person’s name in a variable called famous_person. Then compose your message and store it in a new variable called message. Print your message. ###


```python
quote = "Be the change that you wish to see in the world."
famous_person = "Mahatma Gandhi"
message = f"{famous_person} once said, \"{quote}\""
print(message)
```

    Mahatma Gandhi once said, "Be the change that you wish to see in the world."


### 2-7. Stripping Names: Store a person’s name, and include some whitespace characters at the beginning and end of the name. Make sure you use each character combination, "\t" and "\n", at least once. ###


```python
name = "\tJiyoon\n\n"
print(name)
name = name.lstrip()
print(name)
```

    	Jiyoon
    
    
    Jiyoon
    
    


### 2-8. Number Eight: Write addition, subtraction, multiplication, and division operations that each result in the number 8. Be sure to enclose your operations in print statements to see the results. You should create four lines that look like this: ###
print(5 + 3)


```python
# Jiyoon Choi - 09/26/2022
# This program explores the simple arithmetic in Python: Addition, subtraction, multiplication, and division.
print(2 + 1)
print(8 - 10)
print(3 * 20)
print(33 / 3)
```

    3
    -2
    60
    11.0


### 2-9. Favorite Number: Store your favorite number in a variable. Then, using that variable, create a message that reveals your favorite number. Print that message. ###


```python
# Jiyoon Choi - 09/26/2022
# This program stores a number into a variable called favorite_num, which is included in a message string called message, which is then printed out.
favorite_num = 4
message = f"Believe it or not, my favorite number is {favorite_num} even though it's supposedly the most unlucky number in my culture."
print(message)
```

    Believe it or not, my favorite number is 4 even though it's supposedly the most unlucky number in my culture.


### 2-10. Adding Comments: Choose two of the programs you’ve written, and add at least one comment to each. If you don’t have anything specific to write because your programs are too simple at this point, just add your name and the current date at the top of each program file. Then write one sentence describing what the program does. ###

Added comments to 2-8, 2-9.
