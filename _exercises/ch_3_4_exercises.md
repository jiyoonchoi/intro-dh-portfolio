---
layout: page
title: Exercises Ch. 3-4
description: Completed exercises from Python Crash Course
---

# Chapter 3: Introducing Lists, Chapter 4: Working with Lists #

Course: Intro to Digital Humanities (CLS-161)

Section: Fall 2022

Creator: Jiyoon Choi

### 3-1. Names: Store the names of a few of your friends in a list called names. Print each person’s name by accessing each element in the list, one at a time. ###


```python
names = ['Stephanie', 'Zoe', 'Amanda']
print(names[0])
print(names[1])
print(names[2])
```

    Stephanie
    Zoe
    Amanda


### 3-2. Greetings: Start with the list you used in Exercise 3-1, but instead of just printing each person’s name, print a message to them. The text of each message should be the same, but each message should be personalized with the person’s name. ###


```python
print(f"{names[0]}, how was your day?")
print(f"{names[1]}, how was your day?")
print(f"{names[2]}, how was your day?")
```

    Stephanie, how was your day?
    Zoe, how was your day?
    Amanda, how was your day?


### 3-3. Your Own List: Think of your favorite mode of transportation, such as a motorcycle or a car, and make a list that stores several examples. Use your list to print a series of statements about these items, such as “I would like to own a Honda motorcycle.” ###


```python
car_types = ['Honda', 'Toyota', 'Hyundai', 'Jeep']
print(f"I do like how {car_types[0]} cars look.")
print(f"On the other hand, {car_types[1]}s are reliable vehicles.")
print(f"Can't forget about {car_types[2]}s, they're so nice!")
print(f"I like the boxy shape of a {car_types[3]}.")
```

    I do like how Honda cars look.
    On the other hand, Toyotas are reliable vehicles.
    Can't forget about Hyundais, they're so nice!
    I like the boxy shape of a Jeep.


### 3-4. Guest List: If you could invite anyone, living or deceased, to dinner, who would you invite? Make a list that includes at least three people you’d like to invite to dinner. Then use your list to print a message to each person, inviting them to dinner. ###


```python
invitees = ['Steve Carell', 'Ella Fitzgerald', 'Michael Cera']
print(f"{invitees[0]}, would you like to come to my house for dinner?")
print(f"{invitees[1]}, would you like to come to my house for dinner?")
print(f"{invitees[2]}, would you like to come to my house for dinner?")
```

    Steve Carell, would you like to come to my house for dinner?
    Ella Fitzgerald, would you like to come to my house for dinner?
    Michael Cera, would you like to come to my house for dinner?


### 3-5. Changing Guest List: You just heard that one of your guests can’t make the dinner, so you need to send out a new set of invitations. You’ll have to think of someone else to invite. ###
- Start with your program from Exercise 3-4. Add a print() call at the end of your program stating the name of the guest who can’t make it.
- Modify your list, replacing the name of the guest who can’t make it with the name of the new person you are inviting.
- Print a second set of invitation messages, one for each person who is still in your list.


```python
print(f"{invitees[0]} is unable to make dinner.")
invitees[0] = 'Bob Belcher'
print(f"{invitees[0]}, would you like to come to my house for dinner?")
print(f"{invitees[1]}, would you like to come to my house for dinner?")
print(f"{invitees[2]}, would you like to come to my house for dinner?")
```

    Steve Carell is unable to make dinner.
    Bob Belcher, would you like to come to my house for dinner?
    Ella Fitzgerald, would you like to come to my house for dinner?
    Michael Cera, would you like to come to my house for dinner?


### 3-6. More Guests: You just found a bigger dinner table, so now more space is available. Think of three more guests to invite to dinner. ###

- Start with your program from Exercise 3-4 or Exercise 3-5. Add a print() call to the end of your program informing people that you found a bigger dinner table.
- Use insert() to add one new guest to the beginning of your list.
- Use insert() to add one new guest to the middle of your list.
- Use append() to add one new guest to the end of your list.
- Print a new set of invitation messages, one for each person in your list.


```python
print("Esteemed guests, I have acquired a larger dinner table.")
invitees.insert(1, 'Bob Duncan')
invitees.append('Minnie Mouse')
print(f"{invitees[0]}, would you like to come to my house for dinner?")
print(f"{invitees[1]}, would you like to come to my house for dinner?")
print(f"{invitees[2]}, would you like to come to my house for dinner?")
print(f"{invitees[3]}, would you like to come to my house for dinner?")
print(f"{invitees[4]}, would you like to come to my house for dinner?")
```

    Esteemed guests, I have acquired a larger dinner table.
    Bob Belcher, would you like to come to my house for dinner?
    Bob Duncan, would you like to come to my house for dinner?
    Ella Fitzgerald, would you like to come to my house for dinner?
    Michael Cera, would you like to come to my house for dinner?
    Minnie Mouse, would you like to come to my house for dinner?


### 3-7. Shrinking Guest List: You just found out that your new dinner table won’t arrive in time for the dinner, and you have space for only two guests. ###

- Start with your program from Exercise 3-6. Add a new line that prints a message saying that you can invite only two people for dinner.
- Use pop() to remove guests from your list one at a time until only two names remain in your list. Each time you pop a name from your list, print a message to that person letting them know you’re sorry you can’t invite them to dinner.
- Print a message to each of the two people still on your list, letting them know they’re still invited.
- Use del to remove the last two names from your list, so you have an empty list. Print your list to make sure you actually have an empty list at the end of your program.


```python
invitees = ['Bob Belcher', 'Bob Duncan', 'Ella Fitzgerald', 'Michael Cera', 'Minnie Mouse']
print("My apologies, I have room for only two guests now.")
print(f"{invitees[-1]}, I'm sorry you can't make it to dinner anymore.")
invitees.pop()
print(f"{invitees[-1]}, I'm sorry you can't make it to dinner anymore.")
invitees.pop()
print(f"{invitees[-1]}, I'm sorry you can't make it to dinner anymore.")
invitees.pop()
print(f"{invitees[0]}, you're still invited to dinner.")
print(f"{invitees[1]}, you're still invited to dinner.")
del invitees[-1]
del invitees[-1]
print(invitees)
```

    My apologies, I have room for only two guests now.
    Minnie Mouse, I'm sorry you can't make it to dinner anymore.
    Michael Cera, I'm sorry you can't make it to dinner anymore.
    Ella Fitzgerald, I'm sorry you can't make it to dinner anymore.
    Bob Belcher, you're still invited to dinner.
    Bob Duncan, you're still invited to dinner.
    []


### 3-8. Seeing the World: Think of at least five places in the world you’d like to visit. ###

- Store the locations in a list. Make sure the list is not in alphabetical order.
- Print your list in its original order. Don’t worry about printing the list neatly, just print it as a raw Python list.
- Use sorted() to print your list in alphabetical order without modifying the actual list.
- Show that your list is still in its original order by printing it.
- Use sorted() to print your list in reverse alphabetical order without changing the order of the original list.
- Show that your list is still in its original order by printing it again.
- Use reverse() to change the order of your list. Print the list to show that its order has changed.
- Use reverse() to change the order of your list again. Print the list to show it’s back to its original order.
- Use sort() to change your list so it’s stored in alphabetical order. Print the list to show that its order has been changed.
- Use sort() to change your list so it’s stored in reverse alphabetical order. Print the list to show that its order has changed.


```python
places = ['Narnia', 'Bora Bora', 'Singapore', 'Malaysia', 'Amsterdam']
print(places)
print(sorted(places))
print(places)
print(sorted(places, reverse = True))
print(places)
places.reverse()
print(places)
places.reverse()
print(places)
places.sort()
print(places)
places.sort(reverse = True)
print(places)
```

    ['Narnia', 'Bora Bora', 'Singapore', 'Malaysia', 'Amsterdam']
    ['Amsterdam', 'Bora Bora', 'Malaysia', 'Narnia', 'Singapore']
    ['Narnia', 'Bora Bora', 'Singapore', 'Malaysia', 'Amsterdam']
    ['Singapore', 'Narnia', 'Malaysia', 'Bora Bora', 'Amsterdam']
    ['Narnia', 'Bora Bora', 'Singapore', 'Malaysia', 'Amsterdam']
    ['Amsterdam', 'Malaysia', 'Singapore', 'Bora Bora', 'Narnia']
    ['Narnia', 'Bora Bora', 'Singapore', 'Malaysia', 'Amsterdam']
    ['Amsterdam', 'Bora Bora', 'Malaysia', 'Narnia', 'Singapore']
    ['Singapore', 'Narnia', 'Malaysia', 'Bora Bora', 'Amsterdam']


### 4-1. Pizzas: Think of at least three kinds of your favorite pizza. Store these pizza names in a list, and then use a for loop to print the name of each pizza. ###

- Modify your for loop to print a sentence using the name of the pizza instead of printing just the name of the pizza. - For each pizza you should have one line of output containing a simple statement like I like pepperoni pizza.
- Add a line at the end of your program, outside the for loop, that states how much you like pizza. The output should consist of three or more lines about the kinds of pizza you like and then an additional sentence, such as I really love pizza!


```python
pizzas = ['margharita', 'buffalo chicken', 'hawaiian']
for pizza in pizzas:
    print(f"I like {pizza} pizza.")
print("All in all, I really love pizza!")
```

    I like margharita pizza.
    I like buffalo chicken pizza.
    I like hawaiian pizza.
    All in all, I really love pizza!


### 4-2. Animals: Think of at least three different animals that have a common characteristic. Store the names of these animals in a list, and then use a for loop to print out the name of each animal. ###

Modify your program to print a statement about each animal, such as A dog would make a great pet.
Add a line at the end of your program stating what these animals have in common. You could print a sentence such as Any of these animals would make a great pet!


```python
animals = ['dog', 'platypus', 'human']
for animal in animals:
    print(f"A {animal} is a mammal.")
print("All of these animals are mammals!")
```

    A dog is a mammal.
    A platypus is a mammal.
    A human is a mammal.
    All of these animals are mammals!


### 4-3. Counting to Twenty: Use a for loop to print the numbers from 1 to 20, inclusive. ###


```python
for value in range(1, 21):
    print(value)
```

    1
    2
    3
    4
    5
    6
    7
    8
    9
    10
    11
    12
    13
    14
    15
    16
    17
    18
    19
    20


### 4-6. Odd Numbers: Use the third argument of the range() function to make a list of the odd numbers from 1 to 20. Use a for loop to print each number. ###


```python
for value in range(1, 21, 2):
    print(value)
```

    1
    3
    5
    7
    9
    11
    13
    15
    17
    19


### 4-10. Slices: Using one of the programs you wrote in this chapter, add several lines to the end of the program that do the following: ###

- Print the message The first three items in the list are:. Then use a slice to print the first three items from that program’s list.
- Print the message Three items from the middle of the list are:. Use a slice to print three items from the middle of the list.
- Print the message The last three items in the list are:. Use a slice to print the last three items in the list.

**From 3-8:**


```python
places = ['Narnia', 'Bora Bora', 'Singapore', 'Malaysia', 'Amsterdam']
print(places[0:3])
```

    ['Narnia', 'Bora Bora', 'Singapore']



```python
print(places[1:4])
```

    ['Bora Bora', 'Singapore', 'Malaysia']



```python
print(places[2:5])
```

    ['Singapore', 'Malaysia', 'Amsterdam']


### 4-11. My Pizzas, Your Pizzas: Start with your program from Exercise 4-1 (page 56). Make a copy of the list of pizzas, and call it friend_pizzas. Then, do the following: ###

- Add a new pizza to the original list.
- Add a different pizza to the list friend_pizzas.
- Prove that you have two separate lists. Print the message My favorite pizzas are:, and then use a for loop to print the first list. Print the message My friend’s favorite pizzas are:, and then use a for loop to print the second list. Make sure each new pizza is stored in the appropriate list.


```python
pizzas = ['margharita', 'buffalo chicken', 'hawaiian']
friend_pizzas = pizzas[:]
pizzas.append('cheese')
friend_pizzas.append('veggie')

# printing contents of lists
print("My favorite pizzas are:")
for pizza in pizzas:
    print(pizza)

print("My friend's favorite pizzas are:")
for pizza in friend_pizzas:
    print(pizza)
```

    My favorite pizzas are:
    margharita
    buffalo chicken
    hawaiian
    cheese
    My friend's favorite pizzas are:
    margharita
    buffalo chicken
    hawaiian
    veggie

