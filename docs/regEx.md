# A Concise Guide to Regular Expressions (Regex)

Regular Expressions, or RegEx, are powerful tools used for searching, matching, and manipulating text. Essentially, a RegEx is a sequence of characters that define a search pattern. This is especially useful in tasks involving text processing, such as validating data, extracting information, or transforming text.

Think of RegEx as a sophisticated search tool. For example, instead of manually looking for all email addresses in a document, a RegEx pattern can quickly find and highlight them. The flexibility of RegEx allows you to specify intricate patterns, making it a versatile tool for developers, data scientists, and anyone working with large amounts of text.

While the syntax may appear complex at first, understanding the basics of how RegEx patterns work can significantly enhance your text-processing capabilities. By leveraging the power of RegEx, you can perform tasks that would otherwise be time-consuming and error-prone with precision and efficiency.

Whether you're a beginner or an experienced user, checkout [RegExr](https://regexr.com/) for a user-friendly interface and numerous examples to help you understand and create your own patterns. This website provides an interactive environment where you can test RegEx patterns in real time, ensuring the correctness of your pattern before implementing it in your project.

### [Too Much... or just want something better? Check out STRling!](https://github.com/TheCyberLocal/STRling)

## [⇦ Back to Project Overview](../README.md)

## Table of Contents

- [Literals and Metacharacters](#literals-and-metacharacters)
- [Character Sets](#character-sets)
   - [Predefined Character Sets](#predefined-character-sets)
   - [Custom Character Sets](#custom-character-sets)
   - [Negated Character Sets](#negated-character-sets)
- [Lookarounds](#lookarounds)
- [Special Groups](#special-groups)
   - [Non-Capturing Groups](#non-capturing-groups)
   - [Named Groups](#named-groups)
   - [Atomic Groups](#atomic-groups)
   - [Branch Reset Groups](#branch-reset-groups)
- [Backreferences](#backreferences)
- [Conditional Expressions](#conditional-expressions)
- [Greedy, Lazy, and Possessive Quantifiers](#greedy-lazy-and-possessive-quantifiers)
- [Flags](#flags)
- [Inline Modifiers](#inline-modifiers)
- [Subroutine Calls](#subroutine-calls)
- [Recursion](#recursion)
- [Useful Resources](#useful-resources)

---

## Literals and Metacharacters

[⇧ Back to Table of Contents](#table-of-contents)

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

[⇧ Back to Table of Contents](#table-of-contents)

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

Some uppercase predefined character set matches the negate of its lowercase. For instance, \D matches any character that is not \d.

### Custom Character Sets

- **Syntax**: `[ ]`
- **Description**: Custom character sets are created using square brackets. They match any one of the characters included within the brackets.
- **Examples**: `[abc]` matches `a`, `b`, or `c`; and you can specify ranges like `[a-z]` for any lowercase letter and `[0-9]` for any digit.

### Negated Character Sets

- **Syntax**: `[^ ]`
- **Description**: Negated character sets are created by placing a caret `^` at the beginning of the set within square brackets. They match any single character that is _not_ included in the set.
- **Examples**: `[^abc]` matches any single character that is not `a`, `b`, or `c`.

---

## Lookarounds

[⇧ Back to Table of Contents](#table-of-contents)

   - **Positive Lookahead**: `X(?=Y)` matches `X` if followed by `Y`.
   - **Negative Lookahead**: `X(?!Y)` matches `X` if not followed by `Y`.
   - **Positive Lookbehind**: `(?<=Y)X` matches `X` if preceded by `Y`.
   - **Negative Lookbehind**: `(?<!Y)X` matches `X` if not preceded by `Y`.

## Special Groups

[⇧ Back to Table of Contents](#table-of-contents)

### Non-Capturing Groups
   - **Function**: Groups part of a regex pattern without capturing it.
   - **Syntax**: `(?:pattern)`.
   - **Example**: `(?:foo)bar`.

### Named Groups
   - **Function**: Captures a group and assigns it a name for easy reference.
   - **Syntax**: `(?<name>pattern)` or `(?'name'pattern)`.
   - **Example**: `(?<year>\d{4})-(?<month>\d{2})-(?<day>\d{2})`.

### Atomic Groups
   - **Function**: Prevents the regex engine from backtracking within the group.
   - **Syntax**: `(?>...)`.
   - **Example**: `a(?>b|bc)d` will not match `abcd`, since if it matches the first option, `b`, it continues, without considering `bc`.

### Branch Reset Groups
   - **Function**: Allows capturing groups in different alternatives to have the same number.
   - **Syntax**: `(?|pattern1|pattern2)`.
   - **Example**: `(?|(abc)|(def))` both `abc` and `def` are in Group 1.

## Backreferences

[⇧ Back to Table of Contents](#table-of-contents)

   - **Function**: Refers to the text matched by a previous capturing group.
   - **Syntax**: `\1`, `\2`, ..., `\n` (where `n` is the group number, being the placement of the group's first parenthesis). You can also backreference named capture groups with `\k<name>`.
   - **Example1**: `(\w+)\1` can match `abcabc` or `0101`, since `\1` is whatever `(\w+)` matches.
   - **Example2**: `(?<word>\w+)\k<word>` can match `abcabc` or `0101`, since `k<word>` is whatever `(?<word>\w+)` matches.
   - **Placement**: Given `((a)(b))`, `\1` refers to `((a)(b))`, `\2` refers to `(a)`, and `\3` refers to `(b)`.

## Conditional Expressions

[⇧ Back to Table of Contents](#table-of-contents)

   - **Function**: Matches `true-regex` if `condition` is met; otherwise `false-regex`.
   - **Syntax**: `(?(condition)true-regex|false-regex)`.

## Greedy, Lazy, and Possessive Quantifiers

[⇧ Back to Table of Contents](#table-of-contents)

   - **Greedy**: `*`, `+`, `?` (matches as much as possible)
   - **Lazy**: `*?`, `+?`, `??` (matches as little as possible)
   - **Possessive**: `*+`, `++`, `?+` (like greedy, but without backtracking)

**Possessive Example**: Given `\d++[a-zA-Z]` with string `12345abc`, it matches `12345a`. The `\d++` consumes all digits `12345`, and `[a-zA-Z]` matches the `a`.

## Flags

[⇧ Back to Table of Contents](#table-of-contents)

   - **Function**: Change the behavior of the whole regex.
   - **Syntax**: Using the global flag `g` is done by `/regex/g`.

| Flag                | Syntax | Description                                                    | Example             |
|---------------------|--------|----------------------------------------------------------------|---------------------|
| Case Insensitive    | `i`    | Matches letters in any case.                                   | `/abc/i` matches "AbC", "ABC", "abc", etc. |
| Global Search       | `g`    | Finds all matches.                                             | `/abc/g` finds all occurrences of "abc" in the string. |
| Multiline Mode      | `m`    | `^` and `$` match the start and end of each line, not just the start and end of the string. | `/^abc/m` matches "abc" at the start of any line. |
| Dotall Mode         | `s`    | Dot `.` matches newline characters.                            | `/a.c/s` matches "abc" and "a\nc". |
| Free-Spacing        | `x`    | Whitespace in the pattern (except in a character class) is ignored, and comments are allowed. | `/(?x) a b c # comment/` matches "abc". |


## Inline Modifiers

[⇧ Back to Table of Contents](#table-of-contents)

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

## Subroutine Calls

[⇧ Back to Table of Contents](#table-of-contents)

   - **Function**: Define a group and call it elsewhere in the regex.
   - **Syntax**: `(?(DEFINE)(?<name>pattern))` and `(?&name)`.

## Recursion

[⇧ Back to Table of Contents](#table-of-contents)

   - **Recursion**: For matching nested structures.
   - **Syntax**: `(?R)` for the entire pattern; `(?1)`, `(?2)`, etc., for specific groups.

---

## Useful Resources

[⇧ Back to Table of Contents](#table-of-contents)

- [Regex101](https://regex101.com/): Test and debug regex patterns.
- [MDN Web Docs](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_Expressions): JavaScript regex reference.
- [Regular-Expressions.info](https://www.regular-expressions.info/): Comprehensive regex tutorial and reference.
