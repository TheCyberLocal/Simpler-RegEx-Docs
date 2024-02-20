# A Comprehensive Guide to Markdown Files

## Table of Contents

1. Headers
2. Whitespaces
3. Text Styling
   1. Bold Text
   2. Italic Text
   3. Strikethrough Text
4. Lists
   1. Ordered Lists
   2. Unordered Lists
   3. Checklists
5. Special Text
   1. Blockquotes
   2. Inline Code Snippets
   3. Multi-line Code Samples
   4. Embeding Backtick Strings
6. Tables
7. Section Dividers
8. Emojis
9. Images

---

## Headings

# Heading 1  
**Syntax**: `# Heading 1`.

## Heading 2  
**Syntax**: `## Heading 2`.

... up to

###### Heading 6  
**Syntax**: `###### Heading 6`

Headings 1 and 2 have thin section divdes while 3 through 6 don't.


## Whitespaces  
Single line breaks are ignored and double make a new paragraph; you can also force a single line break with two spaces before the line break, but its not recommended since you have various better alternative styling technices and the spaces are hard to see when creating the format.

## Text Styling

**Example**: **bold text**  
**Syntax**: `**bold text**`

**Example**: *italic text*  
**Syntax**: `*italic text*`

**Example**: ~~strikethrough text~~  
**Syntax**: `~~strikethrough text~~`

## Lists

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

**Syntax1**: `- [x] Completed task`.  
**Syntax2**: `- [ ] Incomplete task`.

## Special Text

### Blockquotes

**Example**:  
> This is a blockquote.

**Syntax**: > This is a blockquote.

### Inline Code Snippets

**Example**: This code here, `sample code`, is perfect.  
**Syntax**: You must use atleast 1 backtick to indicate an inline text block, `` `sample code` ``.

### Multi-line Code Samples

**Syntax**: You must use atleast 3 backticks to indicate a multi-line text block.
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

### Embeding Backtick Stings

You can embed backtick strings inside eachother, but you must use a greater number of backticks for the outer block than for the inner block.

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

| Column 1 | Column 2 |
| - | - |
| Data 1 | Data 2 |
| Data 3 | Data 4 |

\| Column 1 | Column 2 |  
\| - | - |  
\| Data 1 | Data 2 |


## Section Dividers

The line below is a section divide.

---

**Syntax**: `---`.

## Emojis

:tada:
Emojis can be added by copy and pasting, or by using a colon code.  
**Syntax**: `:tada:`.

## Images

**Example**: ![image](https://github.com/TheCyberLocal/styled-coding-notes/assets/93614894/9d6cc948-caef-4b9d-83d4-a98fbd7f3bc2)
**Syntax**: `![alt text](image url or an image or gif asset name)`.
