# Regex

What is Regex?

Regex is short for regular expression. Regex is a sequence of characters that define a search pattern. When included in code or search algorithms, regex can be used to find certain patterns of characters within a string, or to find and replace certain characters within a string. They are frequently used to validate user input, such as email addresses, phone numbers, and passwords.

## Summary

Matching an Email Address with Regex:

The following regex can be used to verify that user input is a valid email address: 
```
/^[a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/
```
Each component of this regex have a unique responsibility to make sure a user enters an email address that begins with an unspecified number of characters preceding the @ symbol, followed by a domain name. The domain name must contain at least one period. The domain name must also end with a valid top-level domain, such as .com, .net, or .org.

Literal characters are the simplest regex. They match themselves exactly. For example, the regex /abc/ matches the string abc.

Meta characters are characters that do not match themselves as literals. Instead, they are interpreted as commands that instruct the regex engine to perform a more complex or refined search. Meta characters include the following:

- . (period) - matches any single character except the newline character
- \w - matches any word character (alphanumeric character plus underscore) 
- \W - matches any non-word character
- \d - matches any digit
- \D - matches any non-digit character
- \s - matches any whitespace character (space, tab, newline, and return)
- \S - matches any non-whitespace character
- \b - matches the empty string, but only at the start or end of a word
- \B - matches the empty string, but not at the start or end of a word
- \0 - matches the null character
- \n - matches a new line character
- \t - matches a tab character
- \v - matches a vertical tab character
- \f - matches a form feed character
- \r - matches a carriage return character
- \xhh - matches the character with the hexadecimal value hh
- \uhhhh - matches the character with the hexadecimal value hhhh
- \cX - matches the control character indicated by X

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Character Classes](#character-classes)
- [Grouping and Capturing](#grouping-and-capturing)
- [Bracket Expressions](#bracket-expressions)
- [Greedy and Lazy Match](#greedy-and-lazy-match)

## Regex Components

### Anchors

Anochors are used to match a pattern at the beginning or end of a string. The ^ symbol is used to match the beginning of a string, and the $ symbol is used to match the end of a string. Anchors are a different breed from literal and meta characters, because they do not match a single character. Instead, they match the position before, after, or between characters. So, applying ^a to abc matches a. ^b does not match abc, because b is not at the beginning of the string.

Similarly, $ matches right after the start of the string. So, applying c$ to abc matches c. Applying a$ to abc does not match, because a is not at the end of the string.

Check Your Understanding:

^ signifies a string that begins with characters that match the pattern that follows the ^ symbol.
$ signifies a string that ends with characters that match the pattern that precedes the $ symbol.

A regex that consists soley of an anchor can only find zero-length matches. This can be useful, but can also create complications.

### Quantifiers

Quantifiers in regex are operators that connect the users email name to the domain name to the top-level domain. A regex quantifier includes + and in this case {2,6}. The + quantifier matches one or more of the preceding token. The {2,6} quantifier matches between two and six of the preceding token.

{2,6} will allow a match of any string that contains at least two characters and at most six characters. For example, the regex /a{2,6}/ matches the string aaaaaa, but not the string a.

### Character Classes

The character class in this expression is \d. As mentioned above, \d matches any digit from 0-9. It will only match a single digit such as 1, but it will not match 11.

### Grouping and Capturing

Grouping and capturing is used to match a pattern and capture the matched text. The parentheses in this regex are used to group the email name, domain name, and top-level domain. The parentheses are also used to capture the matched text.

Capturing groups are numbered by their opening parentheses. The first capturing group is 1, the second is 2, and so on. The 0th capturing group is the entire match. The parentheses are numbered from left to right, and nested parentheses are counted from the leftmost open parenthesis.

In this example, capturing group #1 is:
```
[a-z0-9_\.-]+)
```
This matches the email name.

Capturing group #2 is:
```
([\da-z\.-]+)
```
This matches the domain name.

Capturing group #3 is:
```
([a-z\.]{2,6})
```
This matches the top-level domain. (.com)

### Bracket Expressions

Bracket expressions are used to match a single character out of several possible characters. The bracket expression in this regex is [a-z0-9_\.-]. This matches any lowercase letter from a to z, any digit from 0 to 9, an underscore, a period, or a hyphen.

### Greedy and Lazy Match

Greedy and lazy match is used to match as many characters as possible. The greedy match in this regex is \.([a-z\.]{2,6})$. The greedy match matches as many characters as possible. In this case, the greedy match matches the entire string.

As for lazy match, it matches as few characters as possible.

## Author

Created By: Brittany Burton 2/2023 | Email: b.jenez@icloud.com | Github: 
