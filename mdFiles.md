# A Comprehensive Guide to Markdown Files

## Table of Contents

1. [Headers](#headers)
2. [Anchors](#anchors)
3. [Whitespaces](#whitespaces)
4. [Text Styling](#text-styling)
   1. [Bold Text](#bold-text)
   2. [Italic Text](#italic-text)
   3. [Strikethrough Text](#strikethrough-text)
5. [Lists](#lists)
   1. [Ordered Lists](#ordered-lists)
   2. [Unordered Lists](#unordered-lists)
   3. [Checklists](#checklists)
6. [Special Text](#special-text)
   1. [Blockquotes](#blockquotes)
   2. [Inline Code Snippets](#inline-code-snippets)
   3. [Multi-line Code Samples](#multi-line-code-samples)
   4. [Embedding Backtick Strings](#embedding-backtick-strings)
7. [Tables](#tables)
8. [Section Dividers](#section-dividers)
9. [Emojis](#emojis)
10. [Links](#links)
11. [Images and Gifs with Hover](#images-and-gifs-with-hover)
12. [Linked Images](#linked-images)

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

## Anchors

[⇧ Back to Table of Contents](#table-of-contents)

**Example**: The link directly above that takes you back to the table of contents.

**Syntax**: `[display text](#lowercase-header-with-spaces-as-hyphens)`

**Note:**: This works on any level heading (1-6).

---

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

## Links

[⇧ Back to Table of Contents](#table-of-contents)

**Example**: [My LinkedIn Link](https://www.linkedin.com/in/tzm01/ "Here I am")

**Syntax**: `[display text](redirect link "hover text")`

## Images and Gifs with Hover

[⇧ Back to Table of Contents](#table-of-contents)

**Example**: ![image](/asset.png "I can hover!")

**Syntax**: `![alt text](image link "hover text")`.

Note: The alt text and hover text are entirely optional. `![](image link)`

## Linked Images

[⇧ Back to Table of Contents](#table-of-contents)

**Example**: [![image](/asset.png "I can hover!")](https://www.linkedin.com/in/tzm01/)

**Syntax**: `[![alt text](image link "hover text")](url link)`

**Note:** We use the image syntax in the display text section of the link syntax.
