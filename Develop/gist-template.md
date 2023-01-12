# Email Regular Expression (Email Regex)

This is going to describe a email regular expression and give you a full breakdown of the structure.

## Summary

A regular expression is used to give parameters on special characters for a search pattern in javascript.
Below is an example of one used to search for an email.

`/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`

The string can contain any lowercase letter between a–z

The string can contain any number between 0–9

The string can contain \_ or \ or . or -

The string is between 2-6 characters long

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

A regex needs to be wrapped in `(/)` to be read because it is considered a literal. You can see in the example what this looks like

`/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`

### Anchors

An example of an anchor is `^` or `$`
The `^` is used to describe what is going to be looked for inside of a string
If you write `^Hello` then this will look for a string like `Hello World` but won't find `hello world` because it is case-sensitive.

So in our example `/^([a-z0-9_\.-]` will tell it to look for something that matches the pattern. I will discuss the ranges and quantifiers later on.

### Quantifiers

Quantifiers are used to set the limits of a string that you are searching for. This is typically done to set the min and max length of a given string.

- `*` is used to match the pattern one or two times
- `+` is used to match the pattern one or more times
- `?` is used to match the pattern zero or one time
- `{}` is used in multiple ways to set a limit for matches

  - `{ a }` tells it to match exactly the number given
  - `{ a, }` tells it to match atleast `a` number of times
  - `{ a , x }` tells it to search for a value with a minimum of `a` and a maximum of `x`

  so in our example the `{2,6}` is looking for an ending that is between 2 and 6 characters
  `([a-z\.]{2,6})$`

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
