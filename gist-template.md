# RegEx

## Summary

A **regex**, which is short for **regular expression**, is a sequence of characters that defines a specific search pattern. When included in code or search algorithms, regular expressions can be used to find certain patterns of characters within a string, or to find and replace a character or sequence of characters within a string. They are also frequently used to validate input. 

For example, the following regular expression can be used to verify that user input is a valid email address:

`/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`

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

### Anchors

Three basic topics for ancors are this character below: 
 - ***^The***   match any string that begins with "The"
 - ***end$***   match any string that finishes with "end"
 if you combine both you will get this: 
 - ***^The end$***   an exact match targeting a string that begins with "The" and ends with "end"
 - ***roar***   match any string that posses roar 

### Quantifiers

Quantofiers help us find repeticion after certain character

- ***abc****         match a string that has ab "*" dictates that it has to be followed by zero or more "c". (Ex. ab, abc, abcc will be a match.) 

- ***abc+***        match a string that has ab "+" dictates that it has to be followed by one or more "c".  (Ex. abc, abcc, abccc will be a match.) 

- ***abc?***        match a string that has ab "?" dictates that it has to be followed by zero or one "c".  (Ex. ab, abc, will be a match.) 

- ***abc{2}***      match a string that has ab "{2}" dictates that it has to be followed by 2 "c". (Ex. abcc will be a match.) 

- ***abc{2,}***     match a string that has ab "{2,}" dictates that it has to be followed by 2 or more "c".  (Ex. abcc, abccc, abcccc will be a match.) 

- ***abc{2,5}***    match a string that has ab "{2,5}" dictates that it has to be followed between 2 and 5 "c". (Ex. abcc, abccc, abcccc, abcccc and abccccc will be a match.)

- ***a(bc)****      match a string that has a "(bc)*" dictates that it has to be followed by 2 or 5 copies of the sequence of "bc".  (Ex. abc, abcbc, abcbcbc, etc will be a match.)

### OR Operator
The "or" operator can capture and just match either or letters.

- ***a(b|c)***  match a string that has ab, ac, and captures the match

- ***a[bc]***  it is the almost identical, but the only difference is that it doesnt capture the match.

### Character Classes

- ***\d*** match a single digit 

- ***\w*** match a word character (it covers alphanumerical plus and underscore)

- ***\s*** match a whitespace character (tabs and line breaks)

having the character classes with capital letter will do the inverse of their functionality

### Flags

Flags are usually declare when using these values

- ***g(global)*** does not return after the first match, restarting the subsequent searches from the end of the previous match

- ***m(multi-line)*** if it is combined with ^ and $ it will match the whole string

- ***i(insensitive)*** makes the expression case-insensitive (ex. /aBc/i would match AbC)

### Grouping and Capturing

- ***a(bc)***           parentheses create a capturing group with value bc
- ***a(?:bc)****        using ?: we disable the capturing group 
- ***a(?<foo>bc)***     using ?<foo> we put a name to the group 

### Bracket Expressions

- ***[abc]*** matches a string that has either an "a" or "a" "b" or "a" "c" -> is the same as "a|b|c" 

- ***[a-c]*** same as previous- feels that is like a range a to c

- ***[a-fA-F0-9]*** a string that represents a single hexadecimal digit, case insensitively 

- [0-9]% a string that has a integer character in the range of  0 to 9 before a % sign

- ***[^a-zA-Z]***  a string that does not posses a letter from a to z or from A to Z.

### Greedy and Lazy Match

- ***<.+?>*** matches any character one or more times inside of < >, it can be expand if needed.

- ***<[^<>]+>*** match  any character except < and > one or more times

the ^ is a better solution than the period since it is more strict.

### Boundaries

- ***\babc\b*** it perfoms a search on "whole words only" 

***\b*** is similar to ^ and $ where it can find a single character just like ***\w*** but here it will search the whole word. 

### Back-references

Back-reference are used to match the same text that was match in the first group capturing. Ex. ***([abc])\1*** It can also be used in this was to match the same group more than once. Ex. ***([abc])([de])\2\1*** the back-slash with the number 2 can be used with any other number it will just increase the match in correlation of number of choice. Also ***(?<foo>[abc])\k<foo>*** it will give you the match and the reference.


## Author

Someone lost in the jungle of coding.
Github: [https://github.com/cesarrr93]
