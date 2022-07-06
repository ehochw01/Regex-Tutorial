# Email Validation Regex tutorial

Pattern recognition is a powerful aspect a programming languages. One very common way of expressing patterns in terms of characters are regular expressions, also known as regex. One example of how you can use regex in code is with email validation. You can state the pattern that you want user input to match through a regular expression.

## Summary

An email address must follow some sort of pattern. What is the pattern that a valid email address must be in? When I think of it in layman's terms, I'm thinking that there has to be a string followed by an "@" symbol, followed by some domain name and a ".com" or a ".net", or something like that. How do we indicate this pattern in terms of a regular expression?

Here is the Regex that we will be breaking down:
/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/

This may look like a bunch of mumbo-jumbo now, but I will break this down piece by piece, and explain the different components of regular expressions that are being used here,

First let's start with the first and last characters, the forward slashes. A regex pattern must be wrapped in / for it to be recognized as such.

Next we have the second character: ^
This more or less signifies the start of a pattern. A string that matches this regex would start with whatever literal characters or patter follow the "^". More on this later.

Now onto the first pattern grouping:
([a-z0-9_\.-]+)
This section means that you must have at least one character that is one of the following characters, a-z (a lowercase letter), 0-9 (a digit), '_', '\', '.', or '-'.

@
This is a literal character. You must have an ampersand character in this position. 

([\da-z\.-]+)


- [Anchors](#anchors)
- [Grouping Constructs](#grouping-constructs)
- [Bracket Expressions](#bracket-expressions)
- [Quantifiers](#quantifiers)
- [Character Classes](#character-classes)
- [The OR Operator](#the-or-operator)
- [Character Escapes](#character-escapes)

## Regex Components

### Anchors

### Quantifiers

### Grouping Constructs

### Bracket Expressions

### Character Classes

### The OR Operator

### Flags

### Character Escapes

## Author

A short section about the author with a link to the author's GitHub profile (replace with your information and a link to your profile)

