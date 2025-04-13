# Solutions to Regular Expression Exercises

## Exercise 1: Basic Character Sets
1. **Pattern to match dates in YYYY-MM-DD format:**
   ```
   \d{4}-\d{2}-\d{2}
   ```
   Matches: "2023-12-01", "2025-03-15"

2. **Pattern for alphanumeric identifiers with both letters and numbers:**
   ```
   [A-Za-z][A-Za-z0-9_]*\d+[A-Za-z0-9_]*
   ```
   Matches: "John_Smith123", "Project-X2021", "XB21-9$f5" (part of it)

3. **Pattern for times in HH:MM AM/PM format:**
   ```
   \d{1,2}:\d{2}\sAM|\d{1,2}:\d{2}\sPM
   ```
   Matches: "9:30 AM", "9:42 AM"

## Exercise 2: Predefined Character Classes
4. **Pattern for phone numbers using \d and \w:**
   ```
   \(\d{3}\)\s\d{3}-\d{4}|\+\d-\d{3}-\d{3}-\d{4}
   ```
   Matches: "(555) 123-4567", "+1-555-987-6543"

5. **Pattern for file paths using \s and \S:**
   ```
   [A-Z]:\\[^\s]+|/\S+/
   ```
   Matches: "C:\Projects\Backup\X2021-backup.zip", "C:\Program Files\Project-X\", "/usr/local/bin/project-x/"

6. **Pattern for filenames with version numbers using \w, \d, and \s:**
   ```
   \w+_v\d+\.\d+\.\w+
   ```
   Matches: "main_v3.2.py"

## Exercise 3: Metacharacters and Alternation
7. **Pattern for email addresses or web URLs using pipe operator:**
   ```
   [a-zA-Z0-9_.]+@[a-zA-Z0-9_.]+\.[a-z]+|http://[^\s]+
   ```
   Matches: "anna.director@techcorp.com", "dev.team@techcorp.com", "http://git.techcorp.com/projects/x2021"

8. **Pattern with dot metacharacter to find text in parentheses:**
   ```
   \(.*?\)
   ```
   Matches: "(555) 123-4567", "(IP: 192.168.1.100)"

9. **Pattern for IP addresses:**
   ```
   \d{1,3}\.\d{1,3}\.\d{1,3}\.\d{1,3}
   ```
   Matches: "192.168.1.100"

## Exercise 4: Combined Challenge
10. **Comprehensive pattern for contact information:**
    ```
    [a-zA-Z0-9_.]+@[a-zA-Z0-9_.]+\.[a-z]+|\(\d{3}\)\s\d{3}-\d{4}|\+\d-\d{3}-\d{3}-\d{4}
    ```
    Matches all email addresses and phone numbers in the text
