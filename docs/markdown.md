# A Concise Guide to Markdown Files

Markdown is a lightweight markup language designed for creating formatted text using a simple, easy-to-read syntax. It's particularly popular for writing documentation, README files, and other text that benefits from basic formatting and links.

Markdown allows you to quickly format text with plain text syntax, which is then converted to HTML or other formats. This simplicity makes it ideal for creating clean, readable documentation without needing specialized tools.

Markdown is widely used in software development, note-taking, and static site generators. It is supported by many platforms like GitHub, GitLab, and various content management systems, making it a versatile tool for both individual and collaborative projects.

For those interested in learning more about Markdown, the [Markdown Guide](https://www.markdownguide.org/) is a comprehensive resource. It provides detailed documentation and examples, helping you understand how to use Markdown effectively for your documentation needs.

## [⇦ Back to Documentation Index](../README.md#documentation-index)

## Table of Contents

- [Headers](#headers)
- [Whitespaces](#whitespaces)
- [Text Styling](#text-styling)
   - [Bold Text](#bold-text)
   - [Italic Text](#italic-text)
   - [Strikethrough Text](#strikethrough-text)
- [Lists](#lists)
   - [Ordered Lists](#ordered-lists)
   - [Unordered Lists](#unordered-lists)
   - [Checklists](#checklists)
- [Special Text](#special-text)
   - [Blockquotes](#blockquotes)
   - [Inline Code Snippets](#inline-code-snippets)
   - [Multi-line Code Samples](#multi-line-code-samples)
   - [Embedding Backtick Strings](#embedding-backtick-strings)
- [Tables](#tables)
- [Section Dividers](#section-dividers)
- [Emojis](#emojis)
- [Anchors](#anchors)
- [Links](#links)
- [Images and Gifs with Hover](#images-and-gifs-with-hover)
- [Linked Images](#linked-images)
- [HTML Styling](#html-styling)

---

## Headers

[⇧ Back to Table of Contents](#table-of-contents)

# Heading 1
**Syntax**: `# Heading 1`.

## Heading 2
**Syntax**: `## Heading 2`.

### Heading 3
**Syntax**: `### Heading 3`.

#### Heading 4
**Syntax**: `#### Heading 4`.

##### Heading 5
**Syntax**: `##### Heading 5`.

###### Heading 6
**Syntax**: `###### Heading 6`.

Headings 1 and 2 have thin section dividers while 3 through 6 don't.

## Whitespaces

[⇧ Back to Table of Contents](#table-of-contents)

Single line breaks are ignored, and double line breaks make a new paragraph. You can also force a single line break with two spaces before the line break, but it's not recommended since there are better alternative styling techniques and the spaces are hard to see when creating the format.

## Text Styling

[⇧ Back to Table of Contents](#table-of-contents)

### Bold Text
**Example**: **bold text**
**Syntax**: `**bold text**` or `__bold text__`

### Italic Text
**Example**: *italic text*
**Syntax**: `*italic text*` or `_italic text_`

### Strikethrough Text
**Example**: ~~strikethrough text~~
**Syntax**: `~~strikethrough text~~`

## Lists

[⇧ Back to Table of Contents](#table-of-contents)

### Ordered Lists

**Example**:
1. First Item
   1. First First Item
      1. First First First Item
      2. Second First First Item
   3. Second First Item
2. Second Item

**Syntax**:
```
1. First Item
   1. First First Item
      1. First First First Item
      2. Second First First Item
   3. Second First Item
2. Second Item
```

### Unordered Lists

**Example**:

- Bullet item
- Another bullet item

**Syntax**:
`- Bullet item`
`- Another bullet item`

### Checklists

**Example**: Checklist
- [x] Completed task
- [ ] Incomplete task

**Syntax**: `- [x] Completed task name`.
**Syntax**: `- [ ] Incomplete task name`.

## Special Text

[⇧ Back to Table of Contents](#table-of-contents)

### Blockquotes

**Example**:
> This is a blockquote.

**Syntax**: `> This is a blockquote.`

### Inline Code Snippets

**Example**: This code here, `sample code`, is perfect.
**Syntax**: You must use at least 1 backtick to indicate an inline text block, `` `sample code` ``.

### Multi-line Code Samples

**Syntax**: You must use at least 3 backticks to indicate a multi-line text block.
````
```
multi-line
code sample
demo here
```
````

You can also specify the language of your code for colored styling at the beginning of your code snippet directly after the opening backticks.

**Examples**:
```py
# python code
def hello_world():
    print("Hello, world!")
```

```js
// JavaScript code
function helloWorld() {
    console.log("Hello, world!");
}
```

**Syntax**:
````
```py
# python code
def hello_world():
    print("Hello, world!")
```
````

````
```js
// JavaScript code
function helloWorld() {
    console.log("Hello, world!");
}
```
````

### Embedding Backtick Strings

You can embed backtick strings inside each other, but you must use a greater number of backticks for the outer block than for the inner block.

````
```
``
`
multi-line
code sample
demo here
`
``
```
````

## Tables

[⇧ Back to Table of Contents](#table-of-contents)

**Example**:
| Column 1 | Column 2 |
| - | - |
| Data 1 | Data 2 |
| Data 3 | Data 4 |

**Syntax**:
```
| Column 1 | Column 2 |
| - | - |
| Data 1 | Data 2 |
```

## Section Dividers

[⇧ Back to Table of Contents](#table-of-contents)

The line below is a section divider.

---

**Syntax**: `---`.

## Emojis

[⇧ Back to Table of Contents](#table-of-contents)

:tada:
Emojis can be added by copy and pasting, or by using a colon code.
**Syntax**: `:tada:`.

## Anchors

[⇧ Back to Table of Contents](#table-of-contents)

**Example**: The link directly above that takes you back to the table of contents.

**Syntax**: `[display text](#lowercase-header-with-spaces-as-hyphens)`

**Note**: This works on any level heading (1-6) and can be used alongside a path (./my-file#my-header).

## Links

[⇧ Back to Table of Contents](#table-of-contents)

**Example**: [My LinkedIn Link](https://www.linkedin.com/in/tzm01/ "Here I am")

**Syntax**: `[display text](redirect link "hover text")`

## Images and Gifs with Hover

[⇧ Back to Table of Contents](#table-of-contents)

**Example**: ![image](/assets/hover-effects.png "I can hover!")

**Syntax**: `![alt text](image link "hover text")`.

Note: The alt text and hover text are entirely optional. `![](image link)`

## Linked Images

[⇧ Back to Table of Contents](#table-of-contents)

**Example**: [![image](/assets/hover-effects.png "I can hover!")](https://www.linkedin.com/in/tzm01/)

**Syntax**: `[![alt text](image link "hover text")](url link)`

**Note**: We use the image syntax in the display text section of the link syntax.

## HTML Styling

[⇧ Back to Table of Contents](#table-of-contents)

**Note**: These are just some common uses, but HTML styling has so much more.

**Example**: my<sup>super</sup>text

**Syntax**: `my<sup>super</sup>text`

**Example**: my<sub>sub</sub>text

**Syntax**: `my<sub>sub</sub>text`
