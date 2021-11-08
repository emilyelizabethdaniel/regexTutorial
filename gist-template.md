# Regex Tutorial: a Simple Email Expression

Regex is a powerful tool for programmers to quickly search through text and find patterns. With Regex, you can find things like email addresses, phone numbers, URLs, or words in any language. There are two main ways that regular expressions are used in programming: for parsing strings and for matching strings. Regular expressions are used to define patterns of text, typically for use in pattern matching with strings. They can be quite powerful and expressive, but they have a reputation for being difficult to read.

If you are looking for an efficient way to evaluate a regex email, then this is the article for you. I will walk you through the steps of evaluating your regex with step-by-step instructions on how to do so.

## Summary

This regex snippet is used for varifying email adresses:
/^[a-zA-Z0-9.+_-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,15}$/

At first glance this appears to be a random conglomeration of keys. However I will be going into detail on what each portion means and what it is doing inside of the expression.


## Table of Contents

- [Anchors](#anchors)
- [Bracket Expressions](#bracket-expressions)
- [Quantifiers](#quantifiers)


## Regex Components
To begin we will first take a look at the first and last character of the expression: / and /. All these symbols are doing is delineating where the expression starts and ends, so everything between / and / is the content of the expression.

### Anchors
This expression starts off with an anchor; meaning that it is specifying the location of what you're looking for. Here the anchor is ^: which means to look at the start of the string or a line.
The expression is also ended with an achor as well: $. This anchor simply means the opposite, aka it is looking for the end of a string. 

### Bracket Expressions
Brackets function as a way to find multiple characters: whatever is inside of [], will be searched. This can include numbers or letter characters. the ^ character means here find anything NOT within this range of characters.
In this expression we have 3 sets of brackets:
[a-zA-Z0-9.+_-]  
[a-zA-Z0-9.-]
[a-zA-Z]
We will take a look at the first one:
This expression is searching for any letter between a-z, A-Z (capitals) and the digits 0-9
The . means match any of the +, _, - if found. 

/^[a-zA-Z0-9.+_-]+@ 
We are now up to here, and with what we have just learned, we can start reading the beginning half of this expression. 
Because of the anchor; we know we are looking for the beginning of a string or a line, following that we have the brackets, saying find any characters that match these values. 
After the brackets we have the next bit:
+@
with the + meaning match as many times as possible
and the @
meaning match with the at symbol.

So thus far we know we are looking for something along these lines:

myEmailAdress@

following behind the @ symbol we now have [a-zA-Z0-9.-] again specifying what should follow behind the @.

such as: 
myEmailAdress@email

/^[a-zA-Z0-9.+_-]+@[a-zA-Z0-9.-]+\.

the \. simply means a literal period rather than the metacharacter. So we can add a . on to the end of our current string:
myEmailAdress@email.[a-zA-Z]

or: myEmailAddress@email.com

### Quantifiers
lastly we have reached the final portion: {2,15}$/
Here the {} are there to quanitfy the results found. In the first position the 2 signifies no less than two, and the 15 in the second position signifies no more than 15.
we have now reached the $/ signifying the end of the expression.

## Author
Emily Daniel
https://github.com/emilyelizabethdaniel
