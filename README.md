# Regex Tutorial - Matching an Email

Validating email is one the most common and yet necessary operations in any web project that I can think of. Regular expressions (regex) are patterns used to match character combinations in strings. This tutorial explains how to use a regex to match email addresses.

## Summary

The following expression is used to validate an email address.
```js 
const emailRegex = /^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/g;
```
In order to understand this regex, we'll break it down into components and determine how each one works.

## Table of Contents
- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Character Classes](#character-classes)
- [Flags](#flags)
- [Grouping and Capturing](#grouping-and-capturing)
- [Bracket Expressions](#bracket-expressions)
- [Greedy and Lazy Match](#greedy-and-lazy-match)

## Regex Components

### Anchors ```^ $```

Anchors match a position within a string. 

In our regex:
* `^` Indicates the Starting Position
* `$` Indicates the Ending Position

Validation starts at the beginning of the string provided and finishes at the end of it.

### Quantifiers `+ {n,m}`

Quantifiers specify how many instances of a character, group, or character class must be present in the input for a match to be found. 

In our regex:

* `+` quantifier matches the preceding element one or more times.
  * In `[a-z0-9_\.-]+` the `+` quantifier matches the character set `[a-z0-9_/.-]` one or more times.

* `{n,m}` quantifier matches the preceding element at least n times, but no more than m times, where n and m are integers.
  * In `([a-z\.]{2,6})` the quantifier `{2,6}` matches the previous token (`[a-z\.]`) between 2 and 6 times, as many times as possible.

### Character Classes `a-z, 0-9, /d, /., @`

A character class defines a set of characters, any one of which can occur in an input string for a match to succeed.

In our regex: 

* `a-z` looks for any characters within the range of lowercase a-z.
* `0-9` Looks for any characters within the range of 0 - 9.
* `/d` Matches any digit character (0-9). Equivalent to 0-9.
*  `/.`  Escape Character (period).  Escape sequences can be used to insert reserved, special, and unicode characters. All escaped characters begin with the `\` character.
* `@` Matches any @ character

### Flags `g`

Flags are placed at the end of a regex, after the second slash, and they define additional functionality or limits for the regex. There are six optional flags that can be used, either separately or together and in any order, but in the email validation regex, we only encounter one.

In our regex:

`g` Global search: the regex should be tested against all possible matches in a string.

### Grouping and Capturing `()`

`()` Captures everything enclosed within the parenthesis. It isolates part of the full match and assignes it an ID to be later referred by a back-reference and accessed separately in the results.
 
`/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/g`

In our regex: 

* `([a-z0-9_\.-]+)` looks for any lowercase letter, digit, underscore, hyphen, period in a set prior to the `@` symbol.
* `([\da-z\.-]+)` looks for any digit, lowercase letter, period, or hyphen prior to the escaped period `/.`
* `([a-z\.]{2,6})` looks for between 2-6 characters containing lowercase letters and/or a period.

### Bracket Expressions `[ ]`

A bracket expression encloses a list of character classes within square brackets `[ ]`.

`/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/g`

In our regex:

 * `[a-z0-9_\.-]` looks for any lowercase letter, number, underscore, period, and/or hyphen.
 * `[/da-z.-] ` looks for any digit, lowercase letter, period, and/or hyphen.
 * `[a-z\.] ` looks for any lowercase letter, and/or period.

### Greedy and Lazy Match

Some quantifiers have two versions:

* A greedy version: it tries to match an element as many times as possible.

* A non-greedy (or lazy) version: it tries to match an element as few times as possible. You can turn a greedy quantifier into a lazy quantifier by adding a ?.

In our regex:

* Greedy quantifiers: `+` , `{2,6}`
* No lazy quantifiers 

## Resources

Explore the following resources to expand your knowledge of regex:

* [MDN Web Docs for Regular Expressions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_Expressions)

* [Eloquent JavaScript (Chapter 09): Regular Expressions](https://eloquentjavascript.net/09_regexp.html)

## Author

Hello! My name is JuanJo and I'm a Full-Stack Web Developer. I love to code and write about it.  
Please feel free to contact me using the following links:
* [GitHub: jcuetos97](https://github.com/jcuetos97)
* [Email: jcuetos97@gmail.com](mailto:jcuetos97@gmail.com)
* [LinkedIn: jcuetos97](https://www.linkedin.com/in/jcuetos97/)
* [Website: jcuetos97](https://jcuetos97.github.io/Web-Developer-Portfolio/)
