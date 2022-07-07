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

This more or less signifies the start of a pattern. A string that matches this regex would start with whatever literal characters or pattern follow the "^". More on this later.

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
^ signifies a string that begins with the characters that follow it. This can be an exact string match like "^The", or it can signify a range of possible matches, displayed using [bracket expressions](#bracket-expressions).


**$** signifies a string that ends with the characters that precede it.


### Grouping Constructs
The main grouping construct is a set of paraenthesis: **()**. This is the primary way to group a section of regex and to break up a regex string into parts. Each section within parentheses is known as a subexpression.

### Bracket Expressions
Next we have bracket expression. Anything inside a set of square brackets [] can be considered a set of characters that we want to match. The brackets outline the set of characters we want to include. 
Here are same examples:

**[a-z]** The string can contain any lowercase letter between a–z. 

**[0-9]** The string can contain any number between 0–9.

**[_-]** The string can contain an underscore or hyphen.

A bracket expression can be turned into a negative character group by adding the ^ symbol to the beginning of the expression. Note that this is different than the ^ anchor when '^' is within a bracket expression.

	- e.g. The pattern [^aeiouAEIOU] would find any strings that don't include lowercase or uppercase vowels


### Quantifiers

Quantifiers set the limits of the string that your regex matches (or an individual section of the string). They can specify the number of times a pattern should appear as well as the minimum and maximum character length of a pattern.

_*_ Matches the pattern 0 or more times

**+** Matches the pattern 1 or more times

**?** Matches the pattern 0 or 1 time (it makes a pattern optional)

**{n}** Matches the pattern exactly n number of times

**{n,}** Matches the pattern at least n number of times

**{min,max}** Specifies the min and max length of a pattern

### Character Classes

The are different symbols, or character classes that can signify a set of characters in a regex expression. Here are some examples:

**\\d** any digit (0-9)

**\\w** any character A-Z, a-z, or 0-9

**\\s** whitespace

**.** matches any character except a newline (\\n)

**\\W** anything that isn't a \\w character

**\\S** anything that isn't a \\s character

### Character Escapes

Lastly there are character escpaes which are denoated with a backslash (\\). There are some characters that are a regex component such as '.' and '^'. If you want to denoate a literal '.' in your regex, and not the character class '.' (which matches any character except a newline) you would have to include a backslash before it: (\\.).

#### By Eric Hochwald

[Github Profile](https://github.com/ehochw01?tab=repositories)