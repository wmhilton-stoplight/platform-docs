# Use Markdown in Documentation

Markdown is a markup language for web writers. Markdown allows you to write using an easy-to-read, easy-to-write plain text format, then convert it to structurally valid XHTML or HTML.

In addition to standard Markdown, all Stoplight Design Editors support [Stoplight Flavored Markdown](./stoplight-flavored-markdown.md). Stoplight Flavored Markdown extends CommonMark and adds features like themed callouts and embedded JSON Schema models.

Below is a quick reference of Markdown syntax supported by Stoplight.

## Headers

```md title="Markdown Header Levels"
# H1

## H2

### H3

#### H4

##### H5

###### H6
```
# H1

## H2

### H3

#### H4

##### H5

###### H6

## Emphasis

```md title="Emphasis Examples"
Emphasis, aka italics, with *asterisks* or _underscores_.

Strong emphasis, aka bold, with **asterisks** or __underscores__.

Combined emphasis with **asterisks and _underscores_**.

Strikethrough uses two tildes. ~~Scratch this.~~
```

Emphasis, aka italics, with _asterisks_ or _underscores_.

Strong emphasis, aka bold, with **asterisks** or **underscores**.

Combined emphasis with **asterisks and _underscores_**.

Strikethrough uses two tildes. ~~Scratch this.~~

## Lists

In the following example, leading and trailing spaces are shown with dots.

```md title=Ordered List Example
1. First ordered list item
2. Another item
   ⋅⋅- Unordered sub-list
3. Actual numbers don't matter, just that it's a number
   ⋅⋅1. Ordered sub-list
4. And another item

⋅⋅⋅You can have properly indented paragraphs within list items. Notice the blank line above, and the leading spaces (at least one, but we'll use three here to also align the raw Markdown).
```

1. First ordered list item
2. Another item
   - Unordered sub-list
3. Actual numbers don't matter, just that it's a number
   1. Ordered sub-list
4. And another item

   You can have indented paragraphs within list items. Notice the blank line above, and the leading spaces (at least one, but three spaces here align the raw Markdown).

## Links

```md title=Link Examples
There are two ways to create links:

[This is a basic link](https://www.google.com)

[Hover over this link to see a link title](https://www.google.com "Google's Homepage")

[This is a relative link to the ./stoplight-flavored-markdown.md file](./stoplight-flavored-markdown.md)
```

There are two ways to create links:

[This is a basic link](https://www.google.com)

[Hover over this link to see a link title](https://www.google.com "Google's Homepage")

[This is a relative link to the ./stoplight-flavored-markdown.md file](./stoplight-flavored-markdown.md)

## Images

```md title=Image Example
Here's the Stoplight logo (hover to see the title text):

![Stoplight Logo](https://stoplight.io/images/home/logo-blue-black.png "Stoplight Logo")
```

Here's the Stoplight logo (hover to see the title text):

![Stoplight Logo](https://stoplight.io/images/home/logo-blue-black.png "Stoplight Logo")

To customize images by adding backgrounds, captions or focus, see [images in Stoplight Flavored Markdown](stoplight-flavored-markdown.md).

## Code and Syntax Highlighting

Inline `code` has `back-ticks` around it.

Blocks of code are either fenced by lines with three back-ticks or are indented with four spaces. Fenced code blocks are recommended because they're easier to use and they support syntax highlighting.

<!-- theme: warning -->

> In the examples below, remove the `\` that precedes the three backticks at the start and end of the JavaScript code fence before using.

```
\```js
var s = "JavaScript syntax highlighting";
alert(s);
\```
```

```js
var s = "JavaScript syntax highlighting";
alert(s);
```

Use language tags to change the syntax highlighting:

```
\```json
{
  "JSON": "Syntax Highlighting"
}
\```
```

```json
{
  "JSON": "Syntax Highlighting"
}
```

## Tables

```md  title=Table Examples
Colons can be used to align columns.

| Tables        |      Are      |   Cool |
| ------------- | :-----------: | -----: |
| col 3 is      | right-aligned | \$1600 |
| col 2 is      |   centered    |   \$12 |
| zebra stripes |   are neat    |    \$1 |

There must be at least 3 dashes separating each header cell. The outer pipes (|) are optional, and you don't need to make the raw Markdown line up prettily. You can also use inline Markdown.

| Markdown | Less      | Pretty     |
| -------- | --------- | ---------- |
| _Still_  | `renders` | **nicely** |
| 1        | 2         | 3          |
```

Colons can be used to align columns.

| Tables        |      Are      |   Cool |
| ------------- | :-----------: | -----: |
| col 3 is      | right-aligned | \$1600 |
| col 2 is      |   centered    |   \$12 |
| zebra stripes |   are neat    |    \$1 |

There must be at least 3 dashes separating each header cell. The outer pipes (|) are optional, and you don't need to make the raw Markdown line up prettily. You can also use inline Markdown.

| Markdown | Less      | Pretty     |
| -------- | --------- | ---------- |
| _Still_  | `renders` | **nicely** |
| 1        | 2         | 3          |

## Horizontal Rule

Use three or more asterisks, hyphens, or underscores to add a horizontal rule.

```md
Before.

---

After.
```

Before.

---

After.

### Credits

Most of this information was pulled from [Adam Pritchard's Markdown Cheatsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet). Thank you, Adam, for putting together this cheatsheet!
