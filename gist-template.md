# Regex Tutorial - Finding an Email

## What Is Regex?

A regex, which is short for regular expression, is a sequence of characters that defines a specific search pattern. When included in code or search algorithms, regular expressions can be used to find certain patterns of characters within a string, or to find and replace a character or sequence of characters within a string. They are also frequently used to validate input.

For example, the following regular expression can be used to verify that user input is a valid email address:

/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/

Each component of this regex has a unique responsibility to make sure that a user enters an email address that begins with an unspecified number of characters preceding the @ symbol, followed by a domain.

Regular expression is a way to search through text in an advance way you can do find and replace 

## Summary

Briefly summarize the regex you will be describing and what you will explain. Include a code snippet of the regex. Replace this text with your summary.

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [OR Operator](#or-operator)
- [Character Classes](#character-classes)
- [Flags](#flags)
- [Grouping and Capturing](#grouping-and-capturing)
- [Bracket Expressions](#bracket-expressions)
- [Greedy and Lazy Match](#greedy-and-lazy-match)
- [Boundaries](#boundaries)
- [Back-references](#back-references)
- [Look-ahead and Look-behind](#look-ahead-and-look-behind)

## Regex Components
A regex is considered a literal, so the pattern must be wrapped in slash characters (/). If we examine the “Matching an Email” regex, you'll see that this is true:
```
/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/

```
### Anchors
Anchors are tokens of regex that don't match any of the characters, but the are used to define something about the matching process. The anchor is what starts and ends the regular expression. 

In the email matching regex: 
```
/^([a-z0-9_\.-]+)(@[\da-z\.-]+)\.([a-z\.]{2,6})$/
```

The characters ^ and $ are both considered to be anchors. The ^ anchor tells the expression what characters the string begins with. As the $ tells the expression signifies a string that ends with the characters that precede it.
```
^ signifies that the string must start with [a-z0-9_\.-], Which then says that the email can use an alphabet character from a to z, number from 0 to 9, and can include an underscore, period, or hyphen.

$ signifies the end of the string [a-z\.]{2,6}, can should include an alphabet character that is a to z, because . is a meta character, a \. is used to define a literal dot as a parameter for the expression. The quantifier which is wrapped in curly brackets determines that the end of the string must be between 2 and 6 characters long. 

### Quantifiers



### OR Operator

### Character Classes

### Flags

### Grouping and Capturing

### Bracket Expressions

### Greedy and Lazy Match

### Boundaries

### Back-references

### Look-ahead and Look-behind

## Author

A short section about the author with a link to the author's GitHub profile (replace with your information and a link to your profile)
