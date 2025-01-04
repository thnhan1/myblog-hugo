+++
date = '2025-01-02T21:33:49+07:00'
draft = false
title = 'Hugo-Blog-Awesome Guide'
lang= 'en'
tags = ['hugo', 'blog', 'guide']
categories = ['hugo']
+++

# Emoji support
Turn on emoji support feature in `hugo.toml` by setting `enableEmoji = true`. Or using inline shortcodes. e.g.

`:see_no_evil:` :see_no_evil: `:hear_no_evil:` :hear_no_evil: `:speak_no_evil:` :speak_no_evil:

add font for emoji 

```css
.emoji {
    font-family: Apple Color Emoji, Segoe UI Emoji, NotoColorEmoji, Segoe UI Symbol, Android Emoji, EmojiSymbols;
}
```
Emoji cheat sheet: [Emoji cheat sheet](https://www.webfx.com/tools/emoji-cheat-sheet/)

# Rich content
## YouTube privacy-enhanced shortcode
`privacy="0"` for public, `privacy="1"` for unlisted, `privacy="2"`
for private. e.g.

```md
{{ youtube video_id }}

{{ youtube id="video_id" privacy="0" }}

```

video: Anh la ai? Rap Viet
{{< youtube id="JVZsRaZ6kTA" privacy="0" >}}

# <span style="color: #FFAF61">Markdown syntax guide</span>
## Headings
Using `<h1>`-`<h6>` HTML tags.

## Paragraphs
Separate paragraphs with a blank line.

## Image
- Internal 
`![image](image_path_in_assets)`

![cat](/images/cat.webp)

- External 
`![image](image_url)`

![cat](https://www.google.com/images/branding/googlelogo/1x/googlelogo_color_272x92dp.png)


## Blockquote 
using `> blockquote`

> blockquote
this is a blockquote


## Tables

| name  | age | gender |
|:-----:|:---:|:------:|
| Alice | 20  |   F    |
|  Bob  | 21  |   M    |


## Code Blocks
- Code block with backticks
```java
public class A{
    public static void main(String [] args) {
         System.out.println("hello world!");
    }
}
```
- Code block with 4 space 
    public class A{
        public static void main(String [] args) {
             System.out.println("hello world!");
        }
    }

- Code block with hugo shortcode

{{< highlight html >}} <!doctype html>

<title>Example HTML5 Document</title>
    <p>This is paragraph </p>

{{< /highlight >}}

## Lists 
### Unordered list

```
- item 1
- item 2
```

- item 1
- item 2

### Ordered list
```
1. item 1
2. item 2
```
1. item 1
2. item 2

## Other Elements — abbr, sub, sup, kbd, mark

```html
<abbr title="Graphics Interchange Format">GIF</abbr> is a bitmap image format.

H<sub>2</sub>O

X<sup>n</sup> + Y<sup>n</sup> = Z<sup>n</sup>

Press <kbd>CTRL</kbd>+<kbd>ALT</kbd>+<kbd>Delete</kbd> to end the session.

Most <mark>salamanders</mark> are nocturnal, and hunt for insects, worms, and other small creatures.
```

<abbr title="Graphics Interchange Format">GIF</abbr> is a bitmap image format.

H<sub>2</sub>O

X<sup>n</sup> + Y<sup>n</sup> = Z<sup>n</sup>

Press <kbd>CTRL</kbd>+<kbd>ALT</kbd>+<kbd>Delete</kbd> to end the session.

Most <mark>salamanders</mark> are nocturnal, and hunt for insects, worms, and other small creatures.


## Math formula

support Tex
- enable for globally in `hugo.toml`
```toml
[params]
    math = true
```
- for specific file 
```md
---
math: true
---
```

```md
- Block math:
  $$
  \varphi = 1+\frac{1} {1+\frac{1} {1+\frac{1} {1+\cdots} } }
  $$
- Inline math:
  This is an inline polynomial: $5x^2 + 2y -7$.
```

- Block math:

  $$
  \varphi = 1+\frac{1} {1+\frac{1} {1+\frac{1} {1+\cdots} } }
  $$

- Inline math:

  This is an inline polynomial: $5x^2 + 2y -7$.