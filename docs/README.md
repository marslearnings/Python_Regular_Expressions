# Introduction to Regular Expressions

Regular expressions (regex) are patterns used to match character combinations in strings. These patterns can be simple characters or a combination of simple and special characters.

Examples:
- `/abc/` - A simple pattern matching the literal string "abc"
- `/ab*c/` - A pattern using special characters to match variations

## The Regular Expression Syntax

Regular expressions follow a specific syntax:

- In standard notation: `/pattern/`
- In Python: `r"pattern"`

When a pattern is applied to text, it returns the range where the pattern exists in the string.

## Literals or Simple Characters

Simple literals match the exact characters in the pattern.

Example:
- `/cat/` matches the string "cat" within text

## Meta Characters

Meta characters give regular expressions their power, allowing for more sophisticated matching.

### Special Characters

| Character | Description | Example | Match |
|-----------|-------------|---------|-------|
| \| | Either or | `cat\|hello` | Matches "cat" or "hello" |
| . | Any character (except newline) | `he..lo` | Matches characters between "e" and "l" |
| { } | Exactly specified number of occurrences | `he.{2}o` | Matches "hello" where there are exactly 2 characters between "e" and "o" |
| * | Zero or more occurrences | `he.*o` | Matches "hello", "hero", "helico", etc. |
| + | One or more occurrences | `he.+o` | Same as above but requires at least one character |
| ? | Zero or one occurrence | `he.?o` | Matches "heo" or "hero" |
| ( ) | Capture and group patterns | | |
| [ ] | A set of characters | `[a-z]` | Matches any lowercase letter |
| ^ | Starts with | `^hello` | Matches strings starting with "hello" |
| $ | Ends with | `world$` | Matches strings ending with "world" |
| \ | Signals a special sequence | `\d` | Matches any digit |

### Character Classes

Character classes allow you to define a set of characters where any single character from that set will match.

| Expression | Description |
|------------|-------------|
| `[cs]` | Matches either "c" or "s" (e.g., `/licen[cs]e/` matches "licence" or "license") |
| `[0-9]` | Matches any digit from 0 to 9 |
| `[a-z]` | Matches any lowercase letter |
| `[A-Z]` | Matches any uppercase letter |
| `[0-9a-zA-Z]` | Matches any alphanumeric character |
| `[^0-9]` | Matches any character that is NOT a digit |
| `[^a-z]` | Matches any character that is NOT a lowercase letter |

### Quantifiers

Quantifiers define how many times a character, metacharacter, or character set can be repeated.

| Symbol | Name | Meaning |
|--------|------|---------|
| ? | Question Mark | 0 or 1 repetition |
| * | Asterisk | Zero or more times |
| + | Plus sign | One or more times |
| {n,m} | Curly braces | Between n and m times |

Examples:
- `/hello*/` matches "hell", "hello", "helloo", "hellooo", etc.
- `/hello+/` matches "hello", "helloo", "hellooo", etc. (but not "hell")
- `/hello?/` matches only "hell" or "hello"
- `/hello{2,5}/` matches "helloo", "hellooo", "helloooo", "hellooooo"

## Special Sequence Characters

### Pre-defined Characters

| Character | Description | Equivalent |
|-----------|-------------|------------|
| \w | Word characters (letters, digits, underscore) | `[a-zA-Z0-9_]` |
| \W | NOT word characters | `[^a-zA-Z0-9_]` |
| \d | Digits | `[0-9]` |
| \D | NOT digits | `[^0-9]` |
| \s | Whitespace characters | `[ \t\n\r\f\v]` |
| \S | NOT whitespace characters | `[^ \t\n\r\f\v]` |

## Boundary Characters

Boundary matchers identify specific positions within the input text.

| Matcher | Description |
|---------|-------------|
| ^ | Matches at the beginning of a line |
| $ | Matches at the end of a line |
| \b | Matches a word boundary (beginning or end of word) |
| \B | Matches anything that is NOT a word boundary |
| \A | Matches the beginning of the input |
| \Z | Matches the end of the input |

## Practice Exercises

### Example 1: Basic Pattern Matching

Consider this example string:
```
The quick brown fox jumps over the lazy dog. This is outside (this is inside)
```

| Question | Answer |
|----------|--------|
| Match the string "fox" and provide its range | 16-19 |
| How many times does "is" appear in the string? | 4 |
| Match the pattern "(this is inside)" and provide its range | 61-77 |

### Example 2: Using OR Operator

For the string:
```
The sun rises in the east and sets in the west. Birds sing in the morning or evening.
```

| Question | Pattern |
|----------|---------|
| Match either "sun" or "moon" | `sun\|moon` |
| Match either "east" or "west" | `east\|west` |
| Match either "morning" or "evening" | `morning\|evening` |
| Match either "rises", "sets", or "sing" | `rises\|sets\|sing` |
| Match either "The" or "Birds" | `The\|Birds` |

### Example 3: Contact Information

For this data:
```
Contact Information:
John Doe - john.doe@example.com - (555) 123-4567
Mary Smith - mary_smith@email.net - 555.987.6543
Tom Johnson - tom-johnson@company.org - (555)246-8910
Sarah Brown - sarah@brown.co.uk - +1-555-369-7412
Mike Wilson - mike.wilson@subdomain.example.edu - 555 741 0258
```

| Question | Pattern |
|----------|---------|
| Match any single vowel | `[aeiou]` |
| Match either "John" or "Tom" | `John\|Tom` |
| Match any character that is NOT a digit | `[^0-9]` |
| Match either "com" or "net" in email domains | `com\|net` |
| Match any single digit in phone numbers | `[0-9]` |
| Match any character between 'T' and 'm' in "Tom" | `T.m` |
| Match any single uppercase letter | `[A-Z]` |
| Match any character that is not a letter or number | `[^0-9a-zA-Z]` |

## Warning

The dot (.) is a very powerful metacharacter that can create problems if not used properly, as it matches almost any character.

---

*Source: Data Science Anywhere*

- YouTube: https://www.youtube.com/@datascienceanywhere/
- Udemy: https://www.udemy.com/user/freeai-space/
- GitHub: https://github.com/marslearnings
