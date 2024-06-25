# Module17-challenge: Regex Tutorial 

Have you ever encountered cryptic codes used for searching text? These are likely regular expressions, often shortened to regex. They're special strings that define patterns for finding and managing specific formats within text data.

Imagine you're working with a large document and need to identify all phone numbers or email addresses. Regex empowers you to create a pattern that can recognize these specific structures within the text. This guide will unveil the secrets behind regex using clear examples to make it easier to understand.
## Summary

Let's crack the code! This seemingly complex expression  `/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`  is actually a regular regex expression used to identify email addresses within text. Each symbol plays a specific role in defining the pattern for a valid email address. We'll break down this code step-by-step to understand its meaning.

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

- In the email matching example `/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`, the ^ symbol acts as an anchor at the beginning of the pattern. It ensures that the email address must start with the characters defined within the parentheses ([a-z0-9_\.-]+). This is similar to searching for text that specifically begins with "The".

- On the other hand, the $ symbol serves as an anchor at the end of the pattern. It signifies that a valid email address must conclude with the characters specified within the parentheses ([a-z\.]{2,6}). This functions like searching for text that strictly ends with "end".


### Quantifiers

- Asterisk `*`: Zero or more times (e.g., cde* matches "cde", "cdeee", etc.).
- Plus Sign `+`: One or more times (e.g., cde+ matches "cde", "cdeee", but not "cd").
- Question Mark `?`: Zero or one time (e.g., cde? matches "cd" and "cde").
- Curly Braces `{}`: Exact number of times (e.g., cde{2} matches only "cdee").


### OR Operator

- `|` means or. For example if `abc|xyz`, both `abc` and `xyx` match.
- `[]` functions the same as above. 

### Character Classes

- `\d`: Matches any single digit (0-9).
- `\w`: Matches any single "word character," encompassing letters (a-z, A-Z), digits (0-9), and underscore (_).
- `\s`: Matches any single whitespace character (space, tab, newline, etc.).
- `.`: Matches any single character (except newline by default in some regex flavors).



### Flags

Forward slashes (/) mark the start and end of a regex pattern, not a flag itself. They differentiate the pattern from plain text.

Flags like /g (global) are placed between the slashes to control search behavior. For example, /g finds all occurrences of the pattern, not just the first.

### Grouping and Capturing

`()` = Capture group: remembers what it matches (e.g., c(ba) snags "cba").

`(?:)` = Non-capturing group: matches but forgets (e.g., a(?:bc) matches "abc" or "a").


### Bracket Expressions

Brackets [] define character sets:

- [abc] or a|b|c: Matches any of "a", "b", or "c".
- [a-c]: Matches any character from "a" to "c" (inclusive).
- [a-fA-F0-9]: Matches letters "a-f" (case-insensitive) or digits "0-9".
- [^a-zA-Z]: Matches any character except letters "a-z" or "A-Z".

**Remember**: These brackets create a single matching condition, not multiple.

### Greedy and Lazy Match

Regular expressions use quantifiers (*, +, {}) to specify how many times an element can be repeated. However, these quantifiers can exhibit different matching behaviors:

- **Greedy Search**: By default, these quantifiers are greedy. They try to match the longest possible string that fits the pattern within the text. Imagine them as overzealous eaters, grabbing everything they can.

- **Lazy Search**:  You can activate lazy matching by adding a question mark ? after a quantifier. This flips the behavior, making them match the shortest possible string that still satisfies the pattern. Think of them as picky eaters, taking only what's necessary.

For example, /"?.+?"/g would find any characters between double quotes (") using lazy matching, ensuring it captures only the content within the quotes, not everything until the next quote.

### Boundaries

- `\b` is used to search a whole word. For example if `\bapple\b`, only `apple` will match, no `greenapple` or `redapple`. 

### Back-references

- `([abc])\1` means to match any first letter in the capturing group. For example, it searches for consecutive characters such as `aa`, `aaaaaa`, `bb`, `bbbbbb` and `cc`, `cccccc`. It does not limit how many letters continue.

### Look-ahead and Look-behind

- `d(?=g)` only `d` followed by g matches, for example, `d`g but not dt. G in `d`g is not included in the match.  

- `(?<=f)g` means only `g` preceded by f matches. For example, g in `g`f matches but f is not included in the match.

## Author

[Git hub page for author:](https://github.com/Chadoyek)