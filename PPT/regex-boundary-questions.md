# Regular Expression Boundary Matcher Practice Questions

These questions are based on the following example string:

```
Hello world! This is line one.
World, hello! This is line two.
HelloWorld is a single word.
The word "hello" appears in quotes.
This line ends with hello
hello starts this line and world ends it with world
com.example.domain is a domain name
user@example.com is an email address.
2023-05-15 is a date format.
The final line ends the entire text.
```

## Questions on `^` (Caret) Boundary

1. **Question**: Write a regex pattern that matches any line beginning with the word "Hello".
   **Answer**: `^Hello\b`

2. **Question**: Write a regex pattern that matches any line beginning with either "Hello" or "hello".
   **Answer**: `^[Hh]ello\b`

3. **Question**: How many lines in the example string start with a capital letter?
   **Answer**: 7 lines (all except "hello starts this line..." and "com.example.domain..." and "user@example.com...")

## Questions on `$` (Dollar) Boundary

4. **Question**: Write a regex pattern that matches any line ending with the word "hello".
   **Answer**: `\bhello$`

5. **Question**: How many lines in the example string end with a period?
   **Answer**: 6 lines

6. **Question**: Write a regex pattern that matches any line ending with the exact word "world".
   **Answer**: `\bworld$`

## Questions on `\b` (Word Boundary)

7. **Question**: Write a regex pattern that matches the standalone word "hello" (case-insensitive) in the example text.
   **Answer**: `\b[Hh]ello\b`

8. **Question**: How many times does the standalone word "world" (lowercase only) appear in the example text?
   **Answer**: 3 times

9. **Question**: Write a regex pattern that matches the word "is" only when it appears as a complete word.
   **Answer**: `\bis\b`

## Questions on `\B` (Non-word Boundary)

10. **Question**: Write a regex pattern that matches "World" only when it's part of another word without word boundaries.
    **Answer**: `\BWorld\B`

11. **Question**: In the example text, what word contains "World" without word boundaries on either side?
    **Answer**: "HelloWorld"

12. **Question**: Write a regex that matches "example" when it's part of a larger word or token.
    **Answer**: `\Bexample\B`

## Questions on `\A` (Start of String)

13. **Question**: What single word would a regex pattern `\AHello` match in our example text?
    **Answer**: "Hello" at the very beginning of the entire text

14. **Question**: Write a regex that matches the first 5 characters of the entire example text.
    **Answer**: `\A.{5}`

15. **Question**: How does the pattern `\AThe` perform on our example text?
    **Answer**: It doesn't match anything because "The" is not at the start of the entire string

## Questions on `\z` (End of String)

16. **Question**: Write a regex pattern that matches the last sentence of the entire example text.
    **Answer**: `The final line ends the entire text.\z`

17. **Question**: What's the last word in the entire example text that would be matched by `\w+\.\z`?
    **Answer**: "text"

18. **Question**: Write a regex that matches the last 10 characters of the entire example text.
    **Answer**: `.{10}\z`

## Combined Boundary Questions

19. **Question**: Write a regex that matches lines that both begin with "This" and end with a period.
    **Answer**: `^This.*\.$`

20. **Question**: How many complete lines in the example start with a capital letter and end with a period?
    **Answer**: 5 lines

21. **Question**: Write a regex that matches email addresses that appear as complete standalone words.
    **Answer**: `\b[a-zA-Z0-9._%+-]+@[a-zA-Z0-9.-]+\.[a-zA-Z0-9-]+\b`

22. **Question**: Write a regex that matches the date format in the example, ensuring it stands alone as a complete token.
    **Answer**: `\b\d{4}-\d{2}-\d{2}\b`

23. **Question**: Which lines contain the word "line" as a complete standalone word?
    **Answer**: Lines 1, 2, and 5 ("This is line one.", "This is line two.", "This line ends with hello")

24. **Question**: Write a regex that matches any quotation-enclosed text in the example.
    **Answer**: `"[^"]+"`

25. **Question**: Create a regex that matches the domain name in the email address.
    **Answer**: `@([a-zA-Z0-9.-]+\.[a-zA-Z0-9-]+)`
