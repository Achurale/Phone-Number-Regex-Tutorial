# Phone Number Regex Tutorial
``````
/^(?<CountryCode>\+\d{1,5}[-. ]?)?\(?(?<area>\d{3})([- .\)]+)?(?<prefix>\d{3})[- .]?(?<line>\d{4})$/gm
``````
## Summary

This is a regular expression I wrote from scratch searching for a ten digit phone number, including spaces, periods, or parentheses in the number itself. If a country code is needed, it does support up to 5 digits.

 - `(?<CountryCode>\+\d{1,5}[-. ]?)?` (`+1` 123 456 7890)
    - Checks for an optional country code starting with a + character, optionally ending with a dash, period, or space.

 - `\(?(?<area>\d{3})([- .\)]+)?` (+1 `(123)-`456 7890)
    - The area code of the phone number. Checks for potential parentheses surrounding the area code, along with a dash, period, or space after if one is there.

 - `(?<prefix>\d{3})[- .]?` (+1 123 `456-`7890)
    - The prefix code of the phone number. Checks for a dash, period, or space after.

 - `(?<line>\d{4})$` (+1 123 456 `7890`)
    - The local line code of the phone number.

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
The start `^` and the end `$` of the expression.

### Quantifiers
`[- .\)]+` Will allow numbers with parentheses to work since two characters may be needed to be found (parenthesis + special character).



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