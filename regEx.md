# Comprehensive Guide to Regular Expressions (Regex)

Regular Expressions (Regex) are powerful tools for processing and manipulating text. This guide covers various aspects of regex including syntax, patterns, flags, and advanced features.

---

## Table of Contents

1. Literals and Metacharacters
2. Character Sets
      1.   Predefined Char Sets
      2.   Custom Char Sets
      3.   Negated Char Sets
3. Advanced Features
      1.   Lookarounds
      2.   Backreferences
      3.   Special Groups
            1.   Non-Capturing Groups
            2.   Named Groups
            3.   Atomic Groups
            4.   Branch Reset Groups
      5.   Conditional Expressions
      6.   Greedy, Lazy, and Possessive Quantifiers
      7.   Inline Modifiers and Flags
            1.   Flags
            2.   Inline Modifiers
   7.   Subroutine Calls and Recursion
4. Useful Resources

---

## Literals and Metacharacters

Regex patterns are a combination of characters and special symbols that define search criteria.

- **Literals**: Ordinary characters that match themselves.
- **Metacharacters**: Characters with special meanings.

   | Metacharacter | Description                   |
   |---------------|-------------------------------|
   | `.`           | Matches any single character  |
   | `^`           | Matches the start of a line   |
   | `$`           | Matches the end of a line     |
   | `*`           | Matches 0 or more             |
   | `+`           | Matches 1 or more             |
   | `?`           | Makes the preceding optional  |
   | `-`           | Denotes within a range [a-z]  |
   | `\`           | Used to escape meta characters |
   | `()`          | Used for grouping             |
   | `[]`          | Used for custom character sets |
   | `{}`          | Used as specific quantifiers  |

---

## Character Sets

### Predefined Character Sets

| Predefined Character Sets   | Description                                                               |
|-----------------------------|---------------------------------------------------------------------------|
| `\d`                        | Matches any digit (equivalent to `[0-9]`).                                |
| `\w`                        | Matches any word character (includes letters, digits, and underscores; equivalent to `[a-zA-Z0-9_]`). |
| `\s`                        | Matches any whitespace character (includes spaces, tabs, and line breaks).|
| `\b`                        | Matches a word boundary (the position between a word character and a non-word character).|
| `\n`                        | Matches a newline character.                                              |
| `\t`                        | Matches a tab character.                                                  |
| `\r`                        | Matches a carriage return.                                                |
| `\f`                        | Matches a form feed.                                                      |
| `\v`                        | Matches a vertical tab.                                                   |
| `\0`                        | Matches a NULL character.                                                 |
| `\xhh`                      | Matches the character with the hexadecimal value `hh`.                    |
| `\uhhhh`                    | Matches a Unicode character with the hexadecimal value `hhhh`.            |

Any uppercase predefined character set matches the negate of its lowercase. For instance, \D matches any character that is not \d.

### Custom Character Sets

- **Syntax**: `[ ]`
- **Description**: Custom character sets are created using square brackets. They match any one of the characters included within the brackets.
- **Examples**: `[abc]` matches `a`, `b`, or `c`; and you can specify ranges like `[a-z]` for any lowercase letter and `[0-9]` for any digit.

### Negated Character Sets

- **Syntax**: `[^ ]`
- **Description**: Negated character sets are created by placing a caret `^` at the beginning of the set within square brackets. They match any single character that is _not_ included in the set.
- **Examples**: `[^abc]` matches any single character that is not `a`, `b`, or `c`.

---

## Advanced Features

### Lookarounds
   - **Positive Lookahead**: `X(?=Y)` matches `X` if followed by `Y`.
   - **Negative Lookahead**: `X(?!Y)` matches `X` if not followed by `Y`.
   - **Positive Lookbehind**: `(?<=Y)X` matches `X` if preceded by `Y`.
   - **Negative Lookbehind**: `(?<!Y)X` matches `X` if not preceded by `Y`.

### Backreferences
   - **Function**: Refers to the text matched by a previous capturing group.
   - **Syntax**: `\1`, `\2`, ..., `\n` (where `n` is the group number, being the placement of the group's first parenthesis).
   - **Example**: `(\w+)\1` can match `abcabc` or `xyzxyz`, since `\1` is whatever `(\w+)` matches;
   - **Placement**: Given `((a)(b))`, `\1` refers to `((a)(b))`, `\2` refers to `(a)`, and `\3` refers to `(b)`.

### Special Groups

1.   **Non-Capturing Groups**
      - **Function**: Groups part of a regex pattern without capturing it.
      - **Syntax**: `(?:pattern)`.
      - **Example**: `(?:foo)bar`.

2.   **Named Groups**
      - **Function**: Captures a group and assigns it a name for easy reference.
      - **Syntax**: `(?<name>pattern)` or `(?'name'pattern)`.
      - **Example**: `(?<year>\d{4})-(?<month>\d{2})-(?<day>\d{2})`.

3.   **Atomic Groups**:
      - **Function**: Prevents the regex engine from backtracking within the group.
      - **Syntax**: `(?>...)`.
      - **Example**: `a(?>b|bc)d` will not match `abcd`, since if it matches the first option, `b`, it continues, without considering `bc`.

4.   **Branch Reset Groups**:
      - **Function**: Allows capturing groups in different alternatives to have the same number.
      - **Syntax**: `(?|pattern1|pattern2)`.
      - **Example**: `(?|(abc)|(def))` both `abc` and `def` are in Group 1.

### Conditional Expressions
   - **Function**: Matches `true-regex` if `condition` is met; otherwise `false-regex`.
   - **Syntax**: `(?(condition)true-regex|false-regex)`.

### Greedy, Lazy, and Possessive Quantifiers
   - **Greedy**: `*`, `+`, `?` (matches as much as possible)
   - **Lazy**: `*?`, `+?`, `??` (matches as little as possible)
   - **Possessive**: `*+`, `++`, `?+` (like greedy, but without backtracking)

**Possessive Example**: Given `\d++[a-zA-Z]` with string `12345abc`, it matches `12345a`. The `\d++` consumes all digits `12345`, and `[a-zA-Z]` matches the `a`.

### Inline Modifiers and Flags

#### Flags
   - **Function**: Change the behavior of the whole regex.
   - **Syntax**: Using the global flag `g` is done by `/regex/g`.

| Flag                | Syntax | Description                                                    | Example             |
|---------------------|--------|----------------------------------------------------------------|---------------------|
| Case Insensitive    | `i`    | Matches letters in any case.                                   | `/abc/i` matches "AbC", "ABC", "abc", etc. |
| Global Search       | `g`    | Finds all matches.                                             | `/abc/g` finds all occurrences of "abc" in the string. |
| Multiline Mode      | `m`    | `^` and `$` match the start and end of each line, not just the start and end of the string. | `/^abc/m` matches "abc" at the start of any line. |
| Dotall Mode         | `s`    | Dot `.` matches newline characters.                            | `/a.c/s` matches "abc" and "a\nc". |
| Free-Spacing        | `x`    | Whitespace in the pattern (except in a character class) is ignored, and comments are allowed. | `/(?x) a b c # comment/` matches "abc". |


#### Inline Modifiers
   - **Function**: Change the behavior of only part of the regex.
   - **Syntax**: `(?flags)` for setting, `(?-flags)` for unsetting. 
   - **Example**: `(?i)case insensitive regex(?-i)case sensitive regex`.

| Inline Modifier           | Syntax   | Description                                                        | Example                |
|---------------------------|----------|--------------------------------------------------------------------|------------------------|
| Case Insensitivity        | `(?i)`   | Makes the regex pattern case-insensitive.                          | `(?i)abc` matches 'abc', 'Abc', 'aBc', etc. |
| Multiline Mode            | `(?m)`   | `^` and `$` match the start and end of each line, not just the string. | `(?m)^abc` matches 'abc' at the beginning of any line. |
| Dotall Mode (Single Line) | `(?s)`   | Dot `.` matches newline characters as well.                        | `(?s).+` matches across multiple lines. |
| Free-Spacing and Comments | `(?x)`   | Ignores whitespace in the pattern. Allows comments.                | `(?x) foo \d+ # Matches 'foo' and digits` |
| Ungreedy (Lazy) Mode      | `(?U)`   | Inverts the greediness of quantifiers: quantifiers are lazy by default. | `(?U)a+?b` matches 'ab', 'aab', 'aaab', etc. |
| Combining Modifiers       |          | Multiple modifiers can be combined within the same group.          | `(?im)abc` applies both case-insensitive and multiline modes to `abc`. |

**Notice**: Not all flags can be used as inline modifiers, and not all inline modifiers can be used as flags.

### Subroutine Calls and Recursion
   - **Function**: Define a group and call it elsewhere in the regex.
   - **Syntax**: `(?(DEFINE)(?<name>pattern))` and `(?&name)`.
   - **Recursion**: For matching nested structures.
   - **Syntax**: `(?R)` for the entire pattern; `(?1)`, `(?2)`, etc., for specific groups.

---

## Useful Resources

- [Regex101](https://regex101.com/): Test and debug regex patterns.
- [MDN Web Docs](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_Expressions): JavaScript regex reference.
- [Regular-Expressions.info](https://www.regular-expressions.info/): Comprehensive regex tutorial and reference.
