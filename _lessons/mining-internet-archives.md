---
layout: page
title: Data Mining the Internet Archive Collection
description: This lesson uses Python and Data Mining to retrieve and analyze bibliographic information about items in a collection.
---

## Source

[Caleb McDaniel, "Data Mining the Internet Archive Collection," Programming Historian 3 (2014), https://doi.org/10.46430/phen0035.](https://programminghistorian.org/en/lessons/data-mining-the-internet-archive)

## Reflection



In this lesson, I walked through the tutorial of "Data Mining the Internet Archive Collection" through Programming Historian. This lesson had me create an account through the Internet Archive and access the digital library through terminal in order to follow the steps. 

The Internet Archive (IA) features the Boston Public Library’s anti-slavery collection which, according to the library’s estimates, contains over 16,000 items. Here, we explored this collection using Python and data mining. I learned from this lesson that data mining means extracting and noticing patterns in large data sets. Many of the data in the IA are in a format known as MARC, and here I learned how to download a high volume of MARC files through automation. Also through Python automation, I learned how to parse through these MARC files and search for detailed information like the document's author, for instance.

The key takeaway from this Programming Historian Lesson was the power and robustness of the Internet Archive Collection. Not only is this database massive, but it's completely free and accessible to anybody. Learning to utilize data mining on such an excellent example of a versatile dataset allowed me to gain a better understanding of digital humanities applications.

Data mining can be used in countless other situations, including detecting inconsistencies in large datasets like when bank accounts are flagged for fraudulent activity. This method of data analysis is a technique I had heard about before, but never dove into the meaning of it and its real-world applications until this assignment.

## Code

## Accessing an Internet Archive Collection in Python


```python
# import whole library
import internetarchive
search = internetarchive.search_items('collection:nasa')
print(search.num_found)
```

    206604


## Accessing an Internet Archive Item in Python


```python
item = internetarchive.get_item('lettertowilliaml00doug')
item.download()
```




    []



## Downloading MARC Records from a Collection


```python
import internetarchive

# accessing boston public library archives
search = internetarchive.search_items('collection:bplscas')

# printing identifiers
for result in search:
    print(result['identifier'])
```

## Scraping Information from a MARC Record


```python
import os
import pymarc

path = '/path/to/dir/with/xmlfiles/'

def get_place_of_pub(record):
    try:
        place_of_pub = record['260']['a']
        print(place_of_pub)
    except Exception as e:
        print(e)

for file in os.listdir(path):
    if file.endswith('.xml'):
        pymarc.map_xml(get_place_of_pub, path + file)
```


    ---------------------------------------------------------------------------

    FileNotFoundError                         Traceback (most recent call last)

    Input In [17], in <cell line: 13>()
         10     except Exception as e:
         11         print(e)
    ---> 13 for file in os.listdir(path):
         14     if file.endswith('.xml'):
         15         pymarc.map_xml(get_place_of_pub, path + file)


    FileNotFoundError: [Errno 2] No such file or directory: '/path/to/dir/with/xmlfiles/'

