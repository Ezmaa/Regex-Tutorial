# Regex Tutorial - Finding an Email :email:

## What Is Regex?

A regex, which is short for regular expression, is a sequence of characters that defines a specific search pattern. When included in code or search algorithms, regular expressions can be used to find certain patterns of characters within a string, or to find and replace a character or sequence of characters within a string. They are also frequently used to validate input.

For example, the following regular expression can be used to verify that user input is a valid email address:
```
/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/
```
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
---
Anchors are tokens of regex that don't match any of the characters, but the are used to define something about the matching process. The anchor is what starts and ends the regular expression. 

In the email matching regex: 
```
/^([a-z0-9_\.-]+)(@[\da-z\.-]+)\.([a-z\.]{2,6})$/
```
The characters ^ and $ are both considered to be anchors. The ^ anchor tells the expression what characters the string begins with. As the $ tells the expression signifies a string that ends with the characters that precede it.

^ signifies that the string must start with `[a-z0-9_\.-]`, Which then says that the email can use an alphabet character from a to z, number from 0 to 9, and can include an underscore, period, or hyphen.

$ signifies the end of the string `[a-z\.]{2,6}`, can should include an alphabet character that is a to z, because . is a meta character, a \. is used to define a literal dot as a parameter for the expression. The quantifier which is wrapped in curly brackets determines that the end of the string must be between 2 and 6 characters long. 
### Quantifiers
---
Quantifiers are meta characters that determine how often the characters before the quantifier can occur. 
```
?        occurs 0 or 1 time
+        occurs 1 or more times
*        occurs 0 or more times 
{n}      occurs n times
{n,}     occurs n or more times 
{y,z}    occurs y time, but less than z time 
```
The "+" quantifier means that the characters before the "+" can be one and repeated more times. The {2,6} quantifier means that the items in the bracket must iterate at least twice to generate 2 characters and no more than 6 iterations to generate 6 characters.
### OR Operator
---
The "or" operator "|" allows there to be a choice in matching where the expression matches before or after is acceptable. In this example, there are no "or" operators.
### Character Classes
---
- \	Marks the next character as either a special character or a literal.
- ^	Matches the beginning of input.
- $	Matches the end of input.
- *	Matches the preceding character zero or more times. For example, zo* matches either z or zoo.
- +	Matches the preceding character one or more times. For example, zo+ matches zoo but not z.
- ?	Matches the preceding character zero or one time. For example, a?ve? matches the ve in never.
- .	Matches any single character except a newline character.
(pattern)	Matches a pattern and remembers the match. 
- \A	Matches only at beginning of a string.
- \b	Matches a word boundary, that is, the position between a word and a space. For example, er\b matches the er in never but not the er in verb.
- \B	Matches a nonword boundary. The ea*r\B expression matches the ear in never early.
- \d	Matches a digit character.
- \D	Matches a non-digit character.
- \f	Matches a form-feed character.
- \n	Matches a newline character.
- \r	Matches a carriage return character.
- \s	Matches any white space including spaces, tabs, form-feed characters, and so on.
- \S	Matches any non-white space character.
- \t	Matches a tab character.
- \v	Matches a vertical tab character.
- \w	Matches any word character including underscore. This expression is equivalent to `[A-Za-z0-9_]`.
- \W	Matches any non-word character. This expression is equivalent to `[^A-Za-z0-9_]`.
- \z	Matches only the end of a string.
- \Z	Matches only the end of a string, or before a newline character at the end.

In the email regex `"[a-z]"` represents character between a and z In the expression `/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/` character classes a-z and "\d" are used. This means that a letter a to z and a digit from 0 to 9 can be in the string.
### Flags
---
Flags are arguments that can be used to change the parameters of the expression pattern. 
```
-"i" says to ingore capital casing so that "A" and "a" are considered the same when searching.
-"g" looks for all matches when there is a search.
-"m" affects "^" and "$" behavior across multiple lines when searching.
-"s" enables "dotall" to match newline character. Flags were not used in this email regex.
```
### Grouping and Capturing
---
Grouping and capturing use parethesis to focus on portions of the regex pattern. Then allowing actions like quantifiers to be applied to what is inside the parenthesis. In the expression `/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`, there are three groups, all seperated by parenthesis.
### Bracket Expressions
---
Brackets let the expression search for everything within the brackets. In the beginning of expression `[a-z0-9_\.-]`, the brackets says that the search can be a alphabet from a to z, it can also be a number from 0 to 9, it can be a underscore, or it can be a hyphen.
### Greedy and Lazy Match
---
Greedy refers to your regex matching up to the largest group as possible, lazy means it will match to the smallest group possible. Once the string ends and if the pattern has not completed, the search backtracks by one character attempting to match the next pattern expression. It will continue this step until the pattern is complete or it does not validate. Lazy matching, which has a "?" behind the quantifier, matches the pattern differently. Once a match is made for the expression, the next expression is searched. This email example does not use greedy or lazy matching.
### Boundaries
---
\b represents an anchor similar to $ and ^ where one side is a word character (like \w) and the other side is not a word. \B matches all positions where \b doesn’t match. Boundaries were not used in this email regex.
### Back-references
---
Backreferences match the same text as previously matched by a capturing group. Suppose you want to match a pair of opening and closing HTML tags, and the text in between. By putting the opening tag into a backreference, we can reuse the name of the tag for the closing tag. Back-references were not used in this email regex.
### Look-ahead and Look-behind
---
Look-ahead and Look-behind, collectively called “Look-around”, you can define patterns that only match when they're followed or not followed by another pattern. With look-behind, you can define patterns that only match when they're preceded or followed by another pattern. Look-ahead and Look-behind were not used in this email regex.
## Author
Ezinma Nwankwo 

A driven developer at the University of New Hampshire currently completing a certification in full-stack development.

* Email: ezinmark@gmail.com
* Github: https://github.com/Ezmaa
* LinkedIn: [Ezinma-Nwankwo](linkedin.com/in/ezinma-nwankwo-3b7905234)