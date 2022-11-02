# Regex Tutorial: Matching E-mail

Regex, or Regular Expressions, are used for searching and manipulating text strings. These expressions are incredibly useful as they can replace several lines of code that would accomplish the same thing.

## Summary

This gist will be covering the regex to match an e-mail address. These are useful for making sure an e-mail address matches the correct format, as well as for validation.

`/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Grouping Constructs](#grouping-constructs)
- [Bracket Expressions](#bracket-expressions)
- [Character Classes](#character-classes)
- [The OR Operator](#the-or-operator)
- [Flags](#flags)
- [Character Escapes](#character-escapes)

## Regex Components

### Anchors

Anchors mark the beginning and the end of a string. `^` marks the beginning, this is basically saying that the beginning, or username, of the email adress needs to follow the parameters set within the parentheses following the `^`.

ex: `^([a-z0-9_\.-]+)`

The `$` anchor marks the end of the string, and requires the end of the string, or the domain name, to follow the parameters set within the parentheses before it.

ex: `([a-z\.]{2,6})$`

### Quantifiers

There are two quantifiers used in this regex: `+` and `{x, y}`.

`+` requires the expression to contain one or more of the characters defined in the brackets next to it.

ex: `[a-z0-9_\.-]+`

`{x, y}` denotes length of a string. `x` is the minimum, and `y` is the max. Within this regex specifically, this requires the domain field to be at least 2 characters long, but no more than 6.

ex: `[a-z\.]{2,6}`

### Grouping Constructs

In regular expressions `()` are used to group subexpressions.

ex: `([a-z0-9_\.-]+)`, `([\da-z\.-]+)`, `([a-z\.]{2,6})`

### Bracket Expressions

Within regular expressions, `[]` are used to define acceptable characters within the expression.

ex: `[a-z0-9_\.-]`

This bracket expression requires letters from a to z, numbers from 0 to 9, an underscore, hyphen, or period.

### Character Classes

Character classes are used to define the parameters of a potential character. These can look a few different ways.

ex: `[\da-z\.-]`

This example contains a few character classes. the `/d` in this case denotes that the character defined is a digit. `a-z` matches any letter from `a` to `z`.

### The OR Operator

The OR operator is expressed with the `|` character. It specifies that a character or subexpression may match the characters defined directly before OR directly after the `|`. This regex for matching an e-mail address does not use the `|` OR operator.

### Flags

This regex does not contain any flags. Flags are used after a `/` to give more guidelines to the expression.

ex: `/a/g`

There are a few different flags one could use, i'll define them briefly here.
i = ignore casing
g = global
s = makes the `.` character match newlines as well
m = multiline
y = sticky
u = unicode

### Character Escapes

Sometimes a character within a character class is irregular and without being escaped with a `\` will be interpreted either literally or by its definition within the regex.

ex: `\d`, `\.`

These are escaped characters, the `\d` represents `digit` as opposed to the letter `d`. the `\.` represents the period character instead of the regex meaning of `.` which matches to literally any character except the new line character, `\n`.

## Author

Frank Reynolds, Full Stack Bootcamp student.
https://github.com/fpreynolds
frankpiercereynolds95@gmail.com
