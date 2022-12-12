---
layout: page
title: TEI Exercise
description: Parsing a TEI Document
---
# Parsing a TEI Document - Assignment

## Instructions

1. Parse the tei text of Gibbon's _Decline and Fall_ as found in `gibbon.xml`.
2. Extract all the footnotes and remove extraneous white space.
3. Place footnotes in a dataframe.
4. Save the dataframe as a csv file.

## Parsing TEI


```python
# imports
from bs4 import BeautifulSoup
import re
import pandas as pd
```


```python
# load xml file
with open('../in-class/gibbon.xml', encoding='utf8', mode='r') as f:
    tei_string = f.read()
```


```python
# use BeatifulSoup to insantiate tei object
tei_object = BeautifulSoup(tei_string)
```


```python
# find all margin notes
margin_notes = tei_object.find_all('note', attrs={'place':'margin'})
```


```python
# clean margin notes and add to a list
clean_margin_notes = []
for margin_note in margin_notes:
    margin_note_text = re.sub(r'[\ \n]{2,}', '', margin_note.text)
    clean_margin_notes.append(margin_note_text)
```


```python
# convert list to dataframe
df = pd.DataFrame(clean_margin_notes)
```


```python
# check dataframe
df.head()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>0</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Aureolus invades Italy, is defeated and beſieg...</td>
    </tr>
    <tr>
      <th>1</th>
      <td>A. D. 268.</td>
    </tr>
    <tr>
      <th>2</th>
      <td>A. D. 268. March 20. Death of Gallienus.</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Character and elevation of the emperor Claudius.</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Death of Aureolus.</td>
    </tr>
  </tbody>
</table>
</div>




```python
# save dataframe as csv
df.to_csv('margin_notes.csv')
```
