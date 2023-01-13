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

Inside of a bracket expression the string does not need to exactly match all the parameters.

Therefore you can use the OR expression `(|)` to define your search like this example

`(a|b|c)`

This tells it to look for `a` or `b` or `c `in the string

### Character Classes

A character class is a set of characters that can be used to determine many different inputs in a string as a match.

- `.` is used to match any character except the newline character `\n`
- `\d` is used to match any arabic numeral digit
- `\w` matches any alphanumeric character from the latin alphabet as well as the underscore `_`
- `\s` matches a single white space character that includes a tab input or a line break

### Flags

Flags are used at the end of a regular expression after the closing `/` and define other functionality or rules for the expression.
There are six of these optional flags

- `i` This flag makes the expression ignore capitals. so no difference between `A` and `a`
- `g` This flag makes the expression search for all matches where it would normally stop after the first match
- `m` This flag is for multiline mode
- `u` This flag enables unicode support and enables the processing of surrogate pairs
- `s` This flag enables dotall mode which allows a `.` to match a newline character like `\n`
- `y` This flag is for sticky mode which has it search at the exact position of the text

### Grouping

Grouping constructs are used when a regex gets longer and you need to search for multiple parts of a string to verify it matches
The main way of grouping expressions is using parentheses `()`
The following example uses two groups `(abc):(def)` the colon `:` is used just in the middle of the string so the string to match would look like `abc:def`
this will have it look for an exact match to these characters differently from a bracket expression they will always look for
an exact match unless told otherwise

### Bracket Expressions

Bracket expressions are used to match a range of characters given
putting a hyphen `-` in the middle will give a range from the first input to the next like `[a-z]` will look for any letters from `a` to `z`

- `[a-z]` searches for any lowercase letters in the range of letters given. To look for capitals you need to write `[A-Z]` or combine them to look for both `[a-zA-z]`
- `[0-9]` tells it to look for any number from `0` to `9`
- `[_-]` This shows that the string can contain a underscore `_` or a hyphen `-`. These are special characters and you can search for any special character to be in a string if put inside the brackets and not in between two letters or numbers to prevent searching for a range.

So inside our example `/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/` it is going to look for a range between `a-z` and numbers from `0-9` then multiple special characters then a `@` in the string then we look for arabic digits with `\d` then another range of `a-z` and special characters then the `{2,6}` will look for a string that is `2-6` characters

### Greedy and Lazy Match

A lazy match will only look for the parameters that you are given and ignore anything else in the string.
A greedy match will look for an entire line from beginning to end and will try to capture as much as it can.

You may think that `<.+>` (. means any non newline character and + means one or more) would only match the `<em> and the </em>`, when in reality it will be very greedy, and go from the first `<` to the last `>`. This means it will match `<em>Hello World</em>` instead of what you wanted.

### Boundaries

The character `\b` is an anchor like the caret `^` and the dollar sign `$`. It matches at a position that is called a “word boundary”.
There are multiple spots that are considered a word boundary those are:
Before the first character in the string, if the first character is a word character.
After the last character in the string, if the last character is a word character.
Between two characters in the string, where one is a word character and the other is not a word character.

### Back-references

A back reference will look something like `\1` so in an example `(a-d)\1` this will match `aa` or `bb` or `cc` and also `dd`

### Look-ahead and Look-behind

Lookahead and lookbehind, collectively called “lookaround”, are zero-length assertions just like the start and end of line, and start and end of word anchors explained earlier in this tutorial. The primary difference is lookaround assertions wont consume a string it will just look for a match then drop it and just return whether a match is possible or not. This is why they are called assertions because they just assert whether a match is possible or not. Lookarounds allow you to create regular expressions that would not work without them or would get very long.

## Author

Written by Bryan Smith. Student at University of Irvine california full Stack development bootcamp

GITHUB: https://github.com/smitbry17
