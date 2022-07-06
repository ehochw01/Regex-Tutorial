# Email Validation Regex tutorial

Pattern recognition is a powerful aspect a programming languages. One very common way of expressing patterns in terms of characters are regular expressions, also known as regex. One example of how you can use regex in code is with email validation. You can state the pattern that you want user input to match through a regular expression.

## Summary

An email address must follow some sort of pattern. What is the pattern that a valid email address must be in? When I think of it in layman's terms, I'm thinking that there has to be a string followed by an "@" symbol, followed by some domain name and a ".com" or a ".net", or something like that, at the end of the address. How do we indicate this pattern in terms of a regular expression?

Here is the Regex that we will be breaking down:

**/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/**

This may look like a bunch of mumbo-jumbo now, but I will break this down piece by piece, and explain the different components of regular expressions that are being used here.

First let's start with the first and last characters, the forward slashes: '/'. A regex pattern must be wrapped in '/' for it to be recognized as such. This accounts for the first and last character of the regular expression. 

Next we have the second character: 

**^**

This more or less signifies the start of a pattern. A string that matches this regex would start with whatever literal characters or patter follow the "^". More on this later.

Now onto the first pattern grouping:

**([a-z0-9_\.-]+)**

This section means that you must have at least one character that is one of the following characters, a-z (a lowercase letter), 0-9 (a digit), '_', '\', '.', or '-'.

**@**

This is a literal character. You must have an ampersand character in this position. 

**([\da-z\.-]+)**

This would signify the domain name of the email address. This pattern is the same as the one before the ampersand, but with this time the underscore is omitted. This time, '0-9' is denoted as '/d'. More on this later.

**\\.**

This would be the '.' in '.com' or '.net' etc. The backslash is needed to indicate that the '.' is supposed to be a literal '.' because a '.' can also be a regex operator. 

**([a-z\.]{2,6})**

This would indicate the 'com' or 'net' in '.com' or '.net' respectively. This pattern can have lowercase letters, a '\', as well as a '.'. Another thing to note is that this section of the email adress string can only have a minimum length of 2 and a maximum length of 6.

And finally...

**$**

This signifies a string that ends with the characters that precede it. It denotes the end of the regex. 

Below is a glossary that breaks down the regex component being used in the email validation string. After you review the individual components, the above summary will make a lot more sense. 

- [Anchors](#anchors)
- [Grouping Constructs](#grouping-constructs)
- [Bracket Expressions](#bracket-expressions)
- [Quantifiers](#quantifiers)
- [Character Classes](#character-classes)
- [Character Escapes](#character-escapes)

## Regex Components

### Anchors

### Grouping Constructs

### Bracket Expressions

### Quantifiers

### Character Classes

### Character Escapes

## Eric Hochwald

[Github Profile](https://github.com/ehochw01?tab=repositories)
