---
layout: page
title: Sentiment Analysis for Exploratory Data Analysis
description: This lesson uses Python and the Natural Language Processing Toolkit to perform generate sentiment scores for a text through sentiment analysis.
---
## Source

[Zoë Wilkinson Saldaña, "Sentiment Analysis for Exploratory Data Analysis," Programming Historian 7 (2018), https://doi.org/10.46430/phen0079.](https://programminghistorian.org/en/lessons/sentiment-analysis)

## Reflection

Sentiment analysis is the use of natural language processing to extract subjective information from a textual corpus. It does so by attempting to quantify the emotional intensity of specific words and phrases in the text at hand. In other words, it uses quantitative methods to acquire qualitative data. In this example from the Programming Historian, sentiment analysis is used as the basis for an exploratory data analysis of a case study called "the Enron E-mail Corpus". Exploratory data analysis is essentially a strategy of summarizing or pointing out features of interest within a dataset which would otherwise likely be overlooked. The case study introduces the Enron scandal, where the company Enron was exposed for fraud and the Enron E-mail Corpus contained over 600,000 messages.<br>

I learned a lot from this Programming Historian lesson and enjoyed playing around with VADER and word_tokenize, which are of the Natural Language Processing Toolkit. The idea of sentiment analysis is a highly intuitive concept, and even in its practice I understand how to use the tools provided. Although I don't know the nitty-gritty complex code behind the scenes, as a client I can at least use NPTK appropriate to the scope of my own textual corpus. I found it especially interesting how sentiment analysis still has room to improve in terms of capturing the more complex quirks of human linguistics such as irony, sarcasm, and mockery. Regardless, it's a neat program that can be widely applied.

## Code

## Preparing the Data for Analysis


```python
# first, we import the relevant modules from the NLTK library
from nltk.sentiment.vader import SentimentIntensityAnalyzer
```


```python
# next, we initialize VADER so we can use it within our Python script
sid = SentimentIntensityAnalyzer()
```


```python
# the variable 'message_text' now contains the text we will analyze.
message_text = '''Like you, I am getting very frustrated with this process. I am genuinely trying to be as reasonable as possible. I am not trying to "hold up" the deal at the last minute. I'm afraid that I am being asked to take a fairly large leap of faith after this company (I don't mean the two of you -- I mean Enron) has screwed me and the people who work for me.'''
```

## Analysis Results


```python
print(message_text)

# Calling the polarity_scores method on sid and passing in the message_text outputs a dictionary with negative, neutral, positive, and compound scores for the input text
scores = sid.polarity_scores(message_text)
```

    Like you, I am getting very frustrated with this process. I am genuinely trying to be as reasonable as possible. I am not trying to "hold up" the deal at the last minute. I'm afraid that I am being asked to take a fairly large leap of faith after this company (I don't mean the two of you -- I mean Enron) has screwed me and the people who work for me.



```python
# Here we loop through the keys contained in scores (pos, neu, neg, and compound scores) and print the key-value pairs on the screen
for key in sorted(scores):
        print('{0}: {1}, '.format(key, scores[key]), end='')
```

    compound: -0.3804, neg: 0.093, neu: 0.836, pos: 0.071, 

## Challenge Task: 
Try replacing the contents of message_text with the following strings and re-running the program. Don’t forget to surround each text with three single quotation marks when assigning it to the message_text variable (as in: message_text = ‘'’some words’’‘). Before running the program, guess what you think the sentiment analysis outcome will be: positive, or negative? How strongly positive or negative?

**Example 1**<br><br>
Looks great.  I think we should have a least 1 or 2 real time traders in Calgary.


```python
# updating the variable 'message_text' which contains the text we will analyze.
message_text = '''Looks great. I think we should have a least 1 or 2 real time traders in Calgary.'''
```


```python
# Calling the polarity_scores method on sid and passing in the message_text outputs a dictionary with negative, neutral, positive, and compound scores for the input text
scores = sid.polarity_scores(message_text)
```


```python
# PREDICTION: very positive outcome, not as negative or neutral
# Here we loop through the keys contained in scores (pos, neu, neg, and compound scores) and print the key-value pairs on the screen
for key in sorted(scores):
        print('{0}: {1}, '.format(key, scores[key]), end='')
```

    compound: 0.6249, neg: 0.0, neu: 0.745, pos: 0.255, 

**Example 2**<br><br>
I think we are making great progress on the systems side.  I would like to
set a deadline of November 10th to have a plan on all North American projects
(I'm ok if fundementals groups are excluded) that is signed off on by
commercial, Sally's world, and Beth's world.  When I say signed off I mean
that I want signitures on a piece of paper that everyone is onside with the
plan for each project.  If you don't agree don't sign. If certain projects
(ie. the gas plan) are not done yet then lay out a timeframe that the plan
will be complete.  I want much more in the way of specifics about objectives
and timeframe.

Thanks for everyone's hard work on this.


```python
# updating the variable 'message_text' which contains the text we will analyze.
message_text = '''I think we are making great progress on the systems side. I would like to set a deadline of November 10th to have a plan on all North American projects (I'm ok if fundementals groups are excluded) that is signed off on by commercial, Sally's world, and Beth's world. When I say signed off I mean that I want signitures on a piece of paper that everyone is onside with the plan for each project. If you don't agree don't sign. If certain projects (ie. the gas plan) are not done yet then lay out a timeframe that the plan will be complete. I want much more in the way of specifics about objectives and timeframe.
Thanks for everyone's hard work on this.'''
```


```python
# Calling the polarity_scores method on sid and passing in the message_text outputs a dictionary with negative, neutral, positive, and compound scores for the input text
scores = sid.polarity_scores(message_text)
```


```python
# PREDICTION: more neutral outcome than negative or positive
# Here we loop through the keys contained in scores (pos, neu, neg, and compound scores) and print the key-value pairs on the screen
for key in sorted(scores):
        print('{0}: {1}, '.format(key, scores[key]), end='')
```

    compound: 0.8951, neg: 0.042, neu: 0.821, pos: 0.136, 

**Example 3 (my own)**<br><br>
I really hated the way you designed last week's terrible project proposal.


```python
# updating the variable 'message_text' which contains the text we will analyze.
message_text = '''“I really hated the way you designed last week's terrible project proposal.”'''
```


```python
# Calling the polarity_scores method on sid and passing in the message_text outputs a dictionary with negative, neutral, positive, and compound scores for the input text
scores = sid.polarity_scores(message_text)
```


```python
# PREDICTION: more negative than positive
# Here we loop through the keys contained in scores (pos, neu, neg, and compound scores) and print the key-value pairs on the screen
for key in sorted(scores):
        print('{0}: {1}, '.format(key, scores[key]), end='')
```

    compound: -0.8221, neg: 0.432, neu: 0.568, pos: 0.0, 

## Determine Appropriate Scope for E-mail

**Consider the following text**<br><br>
Message-ID: <3764632.1075857565248.JavaMail.evans@thyme><br>
Date: Mon, 23 Oct 2000 09:14:00 -0700 (PDT)<br>
From: jeffrey.shankman@enron.com<br>
To: john.nowlan@enron.com, don.schroeder@enron.com, david.botchlett@enron.com,<br>
        chris.mahoney@enron.com, ross.koller@enron.com<br>
Subject:<br>
Mime-Version: 1.0<br>
Content-Type: text/plain; charset=us-ascii<br>
Content-Transfer-Encoding: 7bit<br>
X-From: Jeffrey A Shankman<br>
X-To: John L Nowlan, Don Schroeder, David J Botchlett, Chris Mahoney, Ross Koller<br>
X-cc:<br>
X-bcc:<br>
X-Folder: \Jeffrey_Shankman_Jun2001\Notes Folders\Sent<br>
X-Origin: Shankman-J<br>
X-FileName: jshankm.nsf<br>

It seems to me we are in the middle of no man's land with respect to the
following:  Opec production speculation, Mid east crisis and renewed
tensions, US elections and what looks like a slowing economy  (?),  and no
real weather anywhere in the world.  I think it would be most prudent to play
the markets from a very flat price position and try to day trade more
aggressively.  I have no intentions of outguessing Mr. Greenspan, the US.
electorate, the Opec ministers and their new important roles, The Israeli and
Palestinian leaders, and somewhat importantly, Mother Nature.  Given that,
and that we cannot afford to lose any more money, and that Var seems to be a
problem, let's be as flat as possible. I'm ok with spread risk  (not front to
backs, but commodity spreads).<br>


The morning meetings are not inspiring, and I don't have a real feel for
everyone's passion with respect to the markets.  As such, I'd like to ask
John N. to run the morning meetings on Mon. and Wed.


Thanks.   Jeff


```python
# below is the sentiment analysis code rewritten for sentence-level analysis
# note the new module -- word_tokenize!
import nltk.data
from nltk.sentiment.vader import SentimentIntensityAnalyzer
from nltk import sentiment
from nltk import word_tokenize
```


```python
# Next, we initialize VADER so we can use it within our Python script
sid = SentimentIntensityAnalyzer()
```


```python
# We will also initialize our 'english.pickle' function and give it a short name
tokenizer = nltk.data.load('tokenizers/punkt/english.pickle')
```


```python
# Continue with the same code the previous section, but replace the *message_text* variable with the new e-mail text:
message_text = '''It seems to me we are in the middle of no man's land with respect to the  following:  Opec production speculation, Mid east crisis and renewed  tensions, US elections and what looks like a slowing economy (?), and no real weather anywhere in the world. I think it would be most prudent to play  the markets from a very flat price position and try to day trade more aggressively. I have no intentions of outguessing Mr. Greenspan, the US. electorate, the Opec ministers and their new important roles, The Israeli and Palestinian leaders, and somewhat importantly, Mother Nature.  Given that, and that we cannot afford to lose any more money, and that Var seems to be a problem, let's be as flat as possible. I'm ok with spread risk  (not front to backs, but commodity spreads). The morning meetings are not inspiring, and I don't have a real feel for  everyone's passion with respect to the markets.  As such, I'd like to ask  John N. to run the morning meetings on Mon. and Wed.  Thanks. Jeff'''
```


```python
# The tokenize method breaks up the paragraph into a list of strings. In this example, note that the tokenizer is confused by the absence of spaces after periods and actually fails to break up sentences in two instances. How might you fix that?
sentences = tokenizer.tokenize(message_text)

```


```python
# We add the additional step of iterating through the list of sentences and calculating and printing polarity scores for each one.
for sentence in sentences:
        print(sentence)
        scores = sid.polarity_scores(sentence)
        for key in sorted(scores):
                print('{0}: {1}, '.format(key, scores[key]), end='')
        print()
```

    It seems to me we are in the middle of no man's land with respect to the  following:  Opec production speculation, Mid east crisis and renewed  tensions, US elections and what looks like a slowing economy (?
    compound: -0.5267, neg: 0.197, neu: 0.68, pos: 0.123, 
    ), and no real weather anywhere in the world.
    compound: -0.296, neg: 0.216, neu: 0.784, pos: 0.0, 
    I think it would be most prudent to play  the markets from a very flat price position and try to day trade more aggressively.
    compound: 0.0183, neg: 0.103, neu: 0.792, pos: 0.105, 
    I have no intentions of outguessing Mr. Greenspan, the US.
    compound: -0.296, neg: 0.216, neu: 0.784, pos: 0.0, 
    electorate, the Opec ministers and their new important roles, The Israeli and Palestinian leaders, and somewhat importantly, Mother Nature.
    compound: 0.4228, neg: 0.0, neu: 0.817, pos: 0.183, 
    Given that, and that we cannot afford to lose any more money, and that Var seems to be a problem, let's be as flat as possible.
    compound: -0.1134, neg: 0.097, neu: 0.823, pos: 0.081, 
    I'm ok with spread risk  (not front to backs, but commodity spreads).
    compound: -0.0129, neg: 0.2, neu: 0.679, pos: 0.121, 
    The morning meetings are not inspiring, and I don't have a real feel for  everyone's passion with respect to the markets.
    compound: 0.5815, neg: 0.095, neu: 0.655, pos: 0.25, 
    As such, I'd like to ask  John N. to run the morning meetings on Mon.
    compound: 0.3612, neg: 0.0, neu: 0.848, pos: 0.152, 
    and Wed.
    compound: 0.0, neg: 0.0, neu: 1.0, pos: 0.0, 
    Thanks.
    compound: 0.4404, neg: 0.0, neu: 0.0, pos: 1.0, 
    Jeff
    compound: 0.0, neg: 0.0, neu: 1.0, pos: 0.0, 

