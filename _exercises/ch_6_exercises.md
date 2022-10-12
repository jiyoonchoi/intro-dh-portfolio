---
layout: page
title: Exercises Ch. 6
description: Dictionaries
---

# Chapter 6: Dictionaries #

Course: Intro to Digital Humanities (CLS-161)

Section: Fall 2022

Creator: Jiyoon Choi

### 6-1. Person: Use a dictionary to store information about a person you know. Store their first name, last name, age, and the city in which they live. You should have keys such as first_name, last_name, age, and city. Print each piece of information stored in your dictionary. ###


```python
jeana = {'first_name': 'Jeana', 'last_name': 'Choi', 'age': 23, 'city': 'New York City'}
print(jeana['first_name'])
print(jeana['last_name'])
print(jeana['age'])
print(jeana['city'])
```

    Jeana
    Choi
    23
    New York City


### 6-2. Favorite Numbers: Use a dictionary to store people’s favorite numbers. Think of five names, and use them as keys in your dictionary. Think of a favorite number for each person, and store each as a value in your dictionary. Print each person’s name and their favorite number. For even more fun, poll a few friends and get some actual data for your program. ###


```python
fav_nums = {'Robin': 1, 'Ted': 24, 'Barney': 18, 'Lily': 4, 'Marshall': 7}
for person in fav_nums:
    print(f"{person}'s favorite number is {fav_nums[person]}\n")
```

    Robin's favorite number is 1
    
    Ted's favorite number is 24
    
    Barney's favorite number is 18
    
    Lily's favorite number is 4
    
    Marshall's favorite number is 7
    


### 6-3. Glossary: A Python dictionary can be used to model an actual dictionary. However, to avoid confusion, let’s call it a glossary. ###
- Think of five programming words you’ve learned about in the previous chapters. Use these words as the keys in your glossary, and store their meanings as values.
- Print each word and its meaning as neatly formatted output. You might print the word followed by a colon and then its meaning, or print the word on one line and then print its meaning indented on a second line. Use the newline character (\n) to insert a blank line between each word-meaning pair in your output.


```python
glossary = {
    'Boolean': 'A variable type that holds the value of true or false', 
    'For-loop': 'A type of iteration that linearly increments through data',
    'Dictionary': 'A variable type that holds a key-value pair in a list', 
    'Elif': 'A conditional statement that describes an else-if condition', 
    'Float': 'A variable type that holds a decimal value'
}

print(f"Boolean: {glossary['Boolean']}\n")
print(f"For-loop: {glossary['For-loop']}\n")
print(f"Dictionary: {glossary['Dictionary']}\n")
print(f"Elif: {glossary['Elif']}\n")
print(f"Float: {glossary['Float']}\n")
```

    Boolean: A variable type that holds the value of true or false
    
    For-loop: A type of iteration that linearly increments through data
    
    Dictionary: A variable type that holds a key-value pair in a list
    
    Elif: A conditional statement that describes an else-if condition
    
    Float: A variable type that holds a decimal value
    


### 6-4. Glossary 2: Now that you know how to loop through a dictionary, clean up the code from Exercise 6-3 (page 102) by replacing your series of print statements with a loop that runs through the dictionary’s keys and values. When you’re sure that your loop works, add five more Python terms to your glossary. When you run your program again, these new words and meanings should automatically be included in the output. ###


```python
glossary['Print'] = 'To output the data in a format readable to a person'
glossary['Variable'] = 'What you store data into'
glossary['Integer'] = 'A variable type that holds an integer value'
glossary['String'] = 'A variable type that holds a word'
glossary['Append'] = 'To add data onto pre-existing data'

for term in glossary:
    print(f"{term}: {glossary[term]}\n")
```

    Boolean: A variable type that holds the value of true or false
    
    For-loop: A type of iteration that linearly increments through data
    
    Dictionary: A variable type that holds a key-value pair in a list
    
    Elif: A conditional statement that describes an else-if condition
    
    Float: A variable type that holds a decimal value
    
    Print: To output the data in a format readable to a person
    
    Variable: What you store data into
    
    Integer: A variable type that holds an integer value
    
    String: A variable type that holds a word
    
    Append: To add data onto pre-existing data
    


### 6-5. Rivers: Make a dictionary containing three major rivers and the country each river runs through. One key-value pair might be 'nile': 'egypt'. ###
- Use a loop to print a sentence about each river, such as The Nile runs through Egypt.
- Use a loop to print the name of each river included in the dictionary.
- Use a loop to print the name of each country included in the dictionary.


```python
rivers = {
    'nile': 'egypt', 
    'amazon': 'peru', 
    'mississippi': 'united states'
}

for river in rivers:
    print(f"The {river.title()} runs through {rivers[river].title()}\n")
    
for river in rivers:
    print(f"{river.title()}\n")
    
for river in rivers:
    print(f"{rivers[river].title()}\n")
```

    The Nile runs through Egypt
    
    The Amazon runs through Peru
    
    The Mississippi runs through United States
    
    Nile
    
    Amazon
    
    Mississippi
    
    Egypt
    
    Peru
    
    United States
    


### 6-6. Polling: Use the code in favorite_languages.py (page 104). ###

- Make a list of people who should take the favorite languages poll. Include some names that are already in the dictionary and some that are not.
- Loop through the list of people who should take the poll. If they have already taken the poll, print a message thanking them for responding. If they have not yet taken the poll, print a message inviting them to take the poll.


```python
# favorite_languages from pg 104
favorite_languages = {
    'jen': 'python',
    'sarah': 'c',
    'edward': 'ruby',
    'phil': 'python',
}

# my own dictionary
to_ask_poll = {
    'jen': 'python',
    'jiyoon': 'python',
    'cassie': 'c++',
    'edward': 'ruby',
    'rosco': 'r'
}

for person in to_ask_poll:
    if person in favorite_languages:
        print(f"{person.title()}, thank you for taking the poll.")
    else:
        print(f"{person.title()}, I invite you to take the poll.")
```

    Jen, thank you for taking the poll.
    Jiyoon, I invite you to take the poll.
    Cassie, I invite you to take the poll.
    Edward, thank you for taking the poll.
    Rosco, I invite you to take the poll.


### 6-7. People: Start with the program you wrote for Exercise 6-1 (page 102). Make two new dictionaries representing different people, and store all three dictionaries in a list called people. Loop through your list of people. As you loop through the list, print everything you know about each person. ###


```python
# dictionary from 6-1
jeana = {
    'first_name': 'Jeana', 
    'last_name': 'Choi', 
    'age': 23, 
    'city': 'New York City'
}

# next two dictionaries are new
jiyoon = {
    'first_name': 'Jiyoon', 
    'last_name': 'Choi', 
    'age': 19, 
    'city': 'Medford/Somerville'
}

eva = {
    'first_name': 'Eva', 
    'last_name': 'Boruta', 
    'age': 19, 
    'city': 'Boston'
}

people = [jeana, jiyoon, eva]

for person in people:
    print(f"{person['first_name']} {person['last_name']} is {person['age']} years old and lives in {person['city']}\n")
```

    Jeana Choi is 23 years old and lives in New York City
    
    Jiyoon Choi is 19 years old and lives in Medford/Somerville
    
    Eva Boruta is 19 years old and lives in Boston
    


### 6-8. Pets: Make several dictionaries, where the name of each dictionary is the name of a pet. In each dictionary, include the kind of animal and the owner’s name. Store these dictionaries in a list called pets. Next, loop through your list and as you do print everything you know about each pet. ###


```python
marty = {
    'type': 'dog', 
    'owner': 'Stephanie'
}

buttons = {
    'type': 'cat', 
    'owner': 'Christian'
}

hunter = {
    'type': 'dog', 
    'owner': 'Wendy'
}

pets = [marty, buttons, hunter]

for pet in pets:
    print(f"{pet['owner']} owns a {pet['type']}.\n")
```

    Stephanie owns a dog.
    
    Christian owns a cat.
    
    Wendy owns a dog.
    


### 6-9. Favorite Places: Make a dictionary called favorite_places. Think of three names to use as keys in the dictionary, and store one to three favorite places for each person. To make this exercise a bit more interesting, ask some friends to name a few of their favorite places. Loop through the dictionary, and print each person’s name and their favorite places. ###


```python
favorite_places = {
    'Jiyoon': ['Canada', 'Seoul'],
    'Eva': ['Fenway', 'London'],
    'Rena': ['Tokyo', 'Boston']
}

for person, places in favorite_places.items():
    print(f"{person}'s favorite places are:")
    for place in places:
        print("\t" + place)
```

    Jiyoon's favorite places are:
    	Canada
    	Seoul
    Eva's favorite places are:
    	Fenway
    	London
    Rena's favorite places are:
    	Tokyo
    	Boston


### 6-11. Cities: Make a dictionary called cities. Use the names of three cities as keys in your dictionary. Create a dictionary of information about each city and include the country that the city is in, its approximate population, and one fact about that city. The keys for each city’s dictionary should be something like country, population, and fact. Print the name of each city and all of the information you have stored about it. ###


```python
cities = {
    'Seoul': {
            'country': 'South Korea',
            'population': '9.776 million',
            'fact': 'The majority of the people live in the ' 
                    'province surrounding Seoul in the north ' 
                    'west of the country.'
    },
    'London': {
            'country': 'England',
            'population': '8.982 million',
            'fact': 'Over 300 languages are spoken in London.'
    },
    'Tokyo': {
            'country': 'Japan',
            'population': '13.96 million',
            'fact': 'The city was renamed Tokyo, meaning '
                    '\'eastern capital\'. Edo had been ' 
                    'Japan\'s largest city since the 17th century.'
    }
}

for city, info in cities.items():
    print("City: " + city)
    for key, value in info.items():
        print(f"{key.title()}: {value}")
    print()
```

    City: Seoul
    Country: South Korea
    Population: 9.776 million
    Fact: The majority of the people live in the province surrounding Seoul in the north west of the country.
    
    City: London
    Country: England
    Population: 8.982 million
    Fact: Over 300 languages are spoken in London.
    
    City: Tokyo
    Country: Japan
    Population: 13.96 million
    Fact: The city was renamed Tokyo, meaning 'eastern capital'. Edo had been Japan's largest city since the 17th century.
    

