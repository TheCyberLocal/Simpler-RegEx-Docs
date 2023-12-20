Sure, I'll expand the Markdown file to include the other important regex concepts we've discussed previously. This will make the guide more comprehensive.

---

# Comprehensive Guide to Regular Expressions (Regex)

Regular Expressions (Regex) are powerful tools for processing and manipulating text. This guide covers various aspects of regex including syntax, patterns, flags, and advanced features.

## Table of Contents

1. [Basic Syntax](#basic-syntax)
2. [Common Patterns](#common-patterns)
3. [Flags / Modifiers](#flags--modifiers)
4. [Advanced Features](#advanced-features)
5. [Useful Resources](#useful-resources)

## Basic Syntax

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

- **Character Classes**: `[abc]` matches any character a, b, or c.

## Common Patterns

- **Digits**: `\d` matches any digit, equivalent to `[0-9]`.
- **Word Characters**: `\w` matches any word character (letters, digits, and underscores).
- **Whitespace**: `\s` matches any whitespace character (spaces, tabs, line breaks).

## Flags / Modifiers

- **`i` (Case Insensitive)**: Matches letters in any case.
- **`g` (Global Search)**: Finds all matches.
- **`m` (Multiline Mode)**: `^` and `$` match start/end of lines.
- **`s` (Dotall Mode)**: Dot `.` matches newline characters.
- **`x` (Free-Spacing)**: Whitespace in the pattern (except in a character class) is ignored, and comments are allowed.

## Advanced Features

1. **Lookarounds**:

   - **Positive Lookahead**: `X(?=Y)` matches `X` if followed by `Y`.
   - **Negative Lookahead**: `X(?!Y)` matches `X` if not followed by `Y`.
   - **Positive Lookbehind**: `(?<=Y)X` matches `X` if preceded by `Y`.
   - **Negative Lookbehind**: `(?<!Y)X` matches `X` if not preceded by `Y`.

2. **Backreferences**:
   - **Usage**: Refers to the text matched by a previous capturing group.
   - **Syntax**: `\1`, `\2`, ..., `\n` (where `n` is the group number).
   - **Example**: `(abc)\1` matches `abcabc`.

3. **Non-Capturing Groups**: `(?:...)` groups part of a regex without capturing.

4. **Named Groups**: `(?<name>...)` captures a group and assigns it a name.

5. **Atomic Groups**:

   - **Syntax**: `(?>...)`.
   - **Function**: Prevents the regex engine from backtracking within the group.
   - **Example**: `a(?>bc|b)c` will not match `abcc`.

6. **Branch Reset Groups**:

   - **Syntax**: `(?|...)`.
   - **Function**: Alternatives share the same group numbers.
   - **Example**: `(?|(abc)|(def))` both `abc` and `def` are in Group 1.

7. **Conditional Expressions**:

   - **Syntax**: `(?(condition)true-regex|false-regex)`.
   - **Function**: Matches `true-regex` if `condition` is met; otherwise `false-regex`.

8. **Greedy vs. Lazy vs. Possessive Quantifiers**:

   - **Greedy**: `*`, `+`, `?` (matches as much as possible)
   - **Lazy**: `*?`, `+?`, `??` (matches as little as possible)
   - **Possessive**: `*+`, `++`, `?+` (like greedy, but without backtracking)

9. **Inline Modifiers**:

   - **Function**: Change the behavior of part of the regex.
   - **Syntax**: `(?flags)` for setting, `(?-flags)` for unsetting. 
   - **Example**: `(?i)case insensitive(?-i)case sensitive`.

10. **Subroutine Calls and Recursion**:

    - **Subroutine Calls**: Define a group and call it elsewhere in the regex.
    - **Syntax**: `(?(DEFINE)(?<name>pattern))` and `(?&name)`.
    - **Recursion**: For matching nested structures.
    - **Syntax**: `(?R)` for the entire pattern; `(?1)`, `(?2)`, etc., for specific groups.

11. **Comments in Regex**:

    - **In Free-Spacing Mode (`x`)**: Whitespace is ignored, allowing for comments.
    - **Syntax**: `#` for comments.
    - **Example**: `(?x) \d{3} # Match 3 digits`.


## Useful Resources

- [Regex101](https://regex101.com/): Test and debug regex patterns.
- [MDN Web Docs](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_Expressions): JavaScript regex reference.
- [Regular-Expressions.info](https://www.regular-expressions.info/): Comprehensive regex tutorial and reference.

---

This Markdown document now encompasses a wide range of regex topics, including basic syntax, common patterns, modifiers, and several advanced features like lookaheads, lookbehinds, and recursion. This expanded guide serves as a detailed reference for regex usage and functionalities.
