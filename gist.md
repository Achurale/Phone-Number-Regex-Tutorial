# Phone Number Regex Tutorial
``````
/^(?<CountryCode>\+\d{1,5}[-. ]?)?\(?(?<area>\d{3})\)?([- .])?(?<prefix>\d{3})[- .]?(?<line>\d{4})$/gm
``````
## Summary

This is a regular expression I wrote from scratch searching for a ten digit phone number, including spaces, periods, or parentheses in the number itself. If a country code is needed, it does support up to 5 digits.

 - `(?<CountryCode>\+\d{1,5}[-. ]?)?` : (`+1` 123 456 7890)
    - Checks for an optional country code starting with a + character, optionally ending with a dash, period, or space.

 - `\(?(?<area>\d{3})\)?([- .])?` : (+1 `(123)-`456 7890)
    - The area code of the phone number. Checks for potential parentheses surrounding the area code, along with a dash, period, or space after if one is there.

 - `(?<prefix>\d{3})[- .]?` : (+1 123 `456-`7890)
    - The prefix code of the phone number. Checks for a dash, period, or space after.

 - `(?<line>\d{4})$` : (+1 123 456 `7890`)
    - The local line code of the phone number.

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [OR Operator](#or-operator)
- [Character Classes and Bracket Expressions](#character-classes-and-bracket-expressions)
- [Flags](#flags)
- [Grouping and Capturing](#grouping-and-capturing)
- [Greedy and Lazy Match](#greedy-and-lazy-match)

## Regex Components

### Anchors
The start `^` and the end `$` of the expression.

### Quantifiers
Quantifiers give a sort of 'if' statement to the character/group directly behind it.

`\d{1,5} \d{3} \d{3} \d{4}` The `{#}` checks for a string of digits matching the length inside the curly brackets, or a range in the case of the first one. Essentially checking for instances of 'if length= 1 through 5', 'if length = 3', 'if length = 3', and 'if length = 4' altogether.

### Character Classes and Bracket Expressions
Character classes specify what characters are being searched for. In this case, since we're primarily looking for digits/integers, so the character class used is `\d`.

Since we also need a custom grouping of potential special characters, we use a bracket expression. We input the desired characters inside square brackets `[-. ]`, so in between each grouping of numbers there can be one of the characters inside the brackets. Bracket expressions alone check only a single character in its place.

### Flags
Flags affect how the expression checks for things and are tacked on at the very end of the expression. The ones used here are global (`g`) and multiline (`m`). Normally without global it'll check for the first instance matching the expression, global will find multiple groups that match. Multiline makes it so if there is more than one line, it will check all lines instead of just the first one.

### Grouping and Capturing
Groups are shown inside parentheses as shown above in the summary. `(?<line>\d{4})$`
They group up characters and quantifiers together as one. This may help with giving an entire group a quantifier such as the country code being entirely optional with the question mark at the end `(?<CountryCode>\+\d{1,5}[-. ]?)?`. The group has also been named using `?<CountryCode>`.

### Greedy and Lazy Match
A greedy match tries to look for as many matches as possible, while a lazy match looks for as few as possible. No greedy matches are used here, but a there are a lot of lazy matches here looking for optional characters that aren't needed for it to match the expression. The country code in its entirety is also entirely optional.

## Author

I am Achurale, which is a portmanteau of my name. I have always been interested in coding and as of writing this am very much still a student looking forward to learn more.