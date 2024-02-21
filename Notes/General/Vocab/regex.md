Regular expressions (regex) are powerful tools for searching and manipulating text. This cheat sheet provides a quick overview of common elements and examples:

**Characters:**

- **Literal Characters:** Match them exactly (e.g., `a`, `1`, `$`).
- **Wildcard (`*`):** Matches any character (except newline) zero or more times (e.g., `colou?r` matches "color" and "colour").
- **Plus (`+`):** Matches any character one or more times (e.g., `\d+` matches one or more digits).
- **Question Mark (`?`):** Matches the preceding character zero or one time (e.g., `fa?mous` matches "famous" and "famus").
- **Character Classes (`[]`):** Matches any single character within the brackets (e.g., `[aeiou]` matches any vowel).
    
    - Negation (`^` inside `[]`): Matches any character NOT in the brackets (e.g., `[^aeiou]` matches any consonant).
    - Ranges (`-`): Matches characters within a range (e.g., `[a-z]` matches any lowercase letter).
    

**Anchors:**

- **Caret (`^`):** Matches the beginning of the string (e.g., `^hello` matches only "hello").
- **Dollar Sign (`$`):** Matches the end of the string (e.g., `world$` matches only "world").
- **Word Boundary (`\b`):** Matches the beginning or end of a word (e.g., `\bcat\b` matches "cat" but not "category").

**Quantifiers:**

- **Curly Braces (`{n,m}`):** Matches the preceding character n to m times (e.g., `colou{2}` matches "colour" but not "color").

**Grouping:**

- **Parentheses (`()`):** Groups characters together for operations (e.g., `(Mr|Ms)\.` matches "Mr." or "Ms.").

**Backreferences:**

- `\` followed by a number: Matches the content captured by the corresponding numbered group (e.g., `(\d{3})-(\d{3})-(\d{4})`, `$1-$2-$3` extracts phone number parts).

**Flags:**

- **`i`:** Case-insensitive matching (e.g., `Cat` matches "CAT").
- **`m`:** Multiline mode (e.g., `^$` matches empty lines).
- **`s`:** Dot matches any character, including newlines.

**Examples:**

- **Extract email addresses:** `^a-zA-Z0-9.!#$%&'*+/=?^_`{1,63}@[a-zA-Z0-9: ?:[a-zA-Z0-9-]{0,61}[a-zA-Z0-9]?.[a-zA-Z]{2,6}$`
- **Validate US phone numbers:** `^\(?([0-9]{3})\)?[-. ]?([0-9]{3})[-. ]?([0-9]{4})$`
- **Match all words starting with "cat":** `\bcat\w*`