# Regex Tutorial: Matching an Email

Regular expressions (regex) are a string of characters that defines a pattern/ template to help with validation, matching and parsing/ replacing strings. Regex is like creating a template of the criteria that you're looking for in a designated string. The created regex is then compared with the string to filter through the data for any matches to the regex templates requirements.

## Summary

One of the most common applications of regex is matching an email. The following regular expression is an example used to verify a valid email address from the users input:

`
/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/
`

While at first glance it may look like a cat sat on a keyboard, this is a carefully crafted regex that consists of 6 components that work in unison to validate emails. This regex can be broken down into the regex components of: anchors, quantifiers, character classes, grouping and capturing, bracket expressions, and greedy matches. By examing each of these components it will help make the regular expression far easier to understand.

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Character Classes](#character-classes)
- [Grouping and Capturing](#grouping-and-capturing)
- [Bracket Expressions](#bracket-expressions)
- [Greedy Matches](#greedy-matches)

## Regex Components

### Anchors

Anchors in a regular expression don't match with specific characters in a string, but instead assert a set of criteria on the string.

The anchors that were used in the example regex for matching an email are `^` and `$`.

`^` (known as caret or caret anchor) is used to match the begining of a string. 
An example regex using the caret anchor is `^Start` which will match any string that begins with 'Start'.

`$` (dollar sign or dollar anchor) is used to match the end of a string. 
An example regex using the dollar sign is `stop$` which will match any string that ends with 'stop'.

Since the matching an email regex uses both the caret and dollar anchors: 
`
/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/
`
The regex will look to match a string that starts and ends with what's inbetween the two anchors.

### Quantifiers

Quantifiers specify the number of instances of a character, group, or character class may appear in the string so that a match may be found.

The quantifiers that are used in the regex for matching an email are `+` and `{2,6}`.

`+` is used to match the proceeding text 1 or more times.
An example regex using `+` is `asdf+` which will match with strings that contain 'asd' then has 1 or more 'f' following: 'asdf', 'asdff', 'asdfff' would match while `asd` would not.

The matching an email regex uses the `+` quantifier to ensure the email contains `[a-z0-9_\.-]` one or more times before the `@` symbol and `[\da-z\.-]` appears 1 or more times after the `@` symbol.

### Character Classes

The charracter class that is used in the regex for matching an email is `\d`.

`\d` is used to match a single character that is a digit.
An example regex using the `\d` character class is `day\d` which will match any string that starts with 'day' followed by a digit. 'day9' or 'day3' matches while 'dayj' would not.

In the match an email regex the `\d` character class is in the bracket expression `[\da-z\.-]` meaning that it will find a match if a digit, lowercase letter, `.`, or `-` are present.

### Grouping and Capturing

The grouping and capturing that is used in the regex for matching an email is `()`.

`()` is used to group the data inside the brackets and capture it.

In the matching an email regex the `()` brackets appears 3 times: 
`([a-z0-9_\.-]+)` = will group and capture the users email name to be matched
`([\da-z\.-]+)` = will group and capture the email service to be matched
`([a-z\.]{2,6})` = will group and capture the domain extention

### Bracket Expressions

The bracket expression that is used in the regex for matching an email is `[]`.

`[]` is used to match a string that has 1 of the characters inside the square brackets
An example regex using a bracket expression is `[xyz]` which will match any string that starts has the letters 'x' 'y' or 'z' in it. 'fax' or 'may' matches while 'bat' would not.

In the matching an email regex the `[]` bracket expression appears 3 times: 
`[\da-z\.-]` = will match if a digit, any lowercase letter, `.`, or `-` are present.
`[a-z0-9_\.-]` = will match if any lowercase letter, a digit, `_`, `.`, or `-` are present.
`[a-z\.]` = will match if any lowercase letter or `.` are present.

### Greedy Matches

The greedy matches that are used in the regex for matching an email are `+` and `{}`.

## Author

To view more of Justin Collver's work visit their GitHub profile: https://github.com/threewide
