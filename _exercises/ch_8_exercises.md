# Chapter 8: Functions #

Course: Intro to Digital Humanities (CLS-161)

Section: Fall 2022

Creator: Jiyoon Choi

### 8-1. Message: Write a function called display_message() that prints one sentence telling everyone what you are learning about in this chapter. Call the function, and make sure the message displays correctly. ###


```python
def display_message():
    print("I am learning about functions in this chapter.")
    
display_message()
```

    I am learning about functions in this chapter.


### 8-2. Favorite Book: Write a function called favorite_book() that accepts one parameter, title. The function should print a message, such as One of my favorite books is Alice in Wonderland. Call the function, making sure to include a book title as an argument in the function call. ###


```python
def favorite_book(title):
    print(f"One of my favorite books is {title}.")

favorite_book("Alice in Wonderland")
```

    One of my favorite books is Alice in Wonderland.


### 8-3. T-Shirt: Write a function called make_shirt() that accepts a size and the text of a message that should be printed on the shirt. The function should print a sentence summarizing the size of the shirt and the message printed on it. ###
<br>
Call the function once using positional arguments to make a shirt. Call the function a second time using keyword arguments.


```python
def make_shirt(size, text):
    print(f"The size {size} shirt says, '{text}'.")
    
# first call using positional arguments
make_shirt("small", "Keep calm and carry on")

# second call using keyword arguments
make_shirt(size="small", text="Keep calm and carry on")
```

    The size small shirt says, 'Keep calm and carry on'.
    The size small shirt says, 'Keep calm and carry on'.


### 8-5. Cities: Write a function called describe_city() that accepts the name of a city and its country. The function should print a simple sentence, such as Reykjavik is in Iceland. Give the parameter for the country a default value. Call your function for three different cities, at least one of which is not in the default country. ###


```python
def describe_city(city, country="Italy"):
    print(f"{city} is in {country}.")
    
describe_city("Paris", "France")
describe_city("Rome", "Italy")
describe_city("Reykjavik", "Iceland")

# test when omit country to see default
describe_city("Reykjavik")
```

    Paris is in France.
    Rome is in Italy.
    Reykjavik is in Iceland.
    Reykjavik is in Italy.


### 8-6. City Names: Write a function called city_country() that takes in the name of a city and its country. The function should return a string formatted like this: ###
<br>
"Santiago, Chile"
<br><br>
Call your function with at least three city-country pairs, and print the value that’s returned.


```python
def city_country(city, country):
    print(f"{city}, {country}")

city_country("Paris", "France")
city_country("Rome", "Italy")
city_country("Reykjavik", "Iceland")
```

    Paris, France
    Rome, Italy
    Reykjavik, Iceland


### 8-7. Album: Write a function called make_album() that builds a dictionary describing a music album. The function should take in an artist name and an album title, and it should return a dictionary containing these two pieces of information. Use the function to make three dictionaries representing different albums. Print each return value to show that the dictionaries are storing the album information correctly. ###

Add an optional parameter to make_album() that allows you to store the number of tracks on an album. If the calling line includes a value for the number of tracks, add that value to the album’s dictionary. Make at least one new function call that includes the number of tracks on an album.


```python
def make_album(artist, album, tracks=""):
    musician = {
        'artist': artist,
        'album': album
    }
    if tracks:
        musician['tracks'] = tracks
        return musician
    return musician
```


```python
# calling function
omar_apollo = make_album("Omar Apollo", "Ivory", "Evergreen")
audrey_nuna = make_album("AUDREY NUNA", "a liquid breakfast")
men_i_trust = make_album("Men I Trust", "Untourable Album")
```


```python
# printing dictionaries
print(omar_apollo) # calling on artist including tracks
print(audrey_nuna)
print(men_i_trust)
```

    {'artist': 'Omar Apollo', 'album': 'Ivory', 'tracks': 'Evergreen'}
    {'artist': 'AUDREY NUNA', 'album': 'a liquid breakfast'}
    {'artist': 'Men I Trust', 'album': 'Untourable Album'}

