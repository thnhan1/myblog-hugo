+++
date = '2025-01-02T21:33:49+07:00'
draft = false
title = 'Hướng Dẫn Hugo-Blog-Awesome'
lang= 'vi'
tags = ['hugo', 'blog', 'guide']
categories = ["hugo"]
+++

# Hỗ trợ Emoji
Bật tính năng hỗ trợ emoji trong `hugo.toml` bằng cách đặt `enableEmoji = true`. Hoặc sử dụng inline shortcodes. Ví dụ:

`:see_no_evil:` :see_no_evil: `:hear_no_evil:` :hear_no_evil: `:speak_no_evil:` :speak_no_evil:

thêm font cho emoji

```css
.emoji {
  font-family: Apple Color Emoji, Segoe UI Emoji, NotoColorEmoji, Segoe UI Symbol, Android Emoji, EmojiSymbols;
}
```
Bảng cheat sheet Emoji: [Emoji cheat sheet](https://www.webfx.com/tools/emoji-cheat-sheet/)

# Nội dung phong phú
## Shortcode YouTube bảo mật cao
`privacy="0"` cho công khai, `privacy="1"` cho không công khai, `privacy="2"` cho riêng tư. Ví dụ:

```md
{{ youtube video_id }}

{{ youtube id="video_id" privacy="0" }}

```

video: Anh là ai? Rap Việt
{{< youtube id="JVZsRaZ6kTA" privacy="0" >}}

# <span style="color: #FFAF61">Hướng dẫn cú pháp Markdown</span>
## Tiêu đề
Sử dụng thẻ HTML `<h1>`-`<h6>`.

## Đoạn văn
Tách các đoạn văn bằng một dòng trống.

## Hình ảnh
- Nội bộ 
`![image](image_path_in_assets)`

![cat](/images/cat.webp)

- Bên ngoài 
`![image](image_url)`

![cat](https://www.google.com/images/branding/googlelogo/1x/googlelogo_color_272x92dp.png)


## Trích dẫn 
sử dụng `> blockquote`

> blockquote
đây là một trích dẫn


## Bảng

| tên   | tuổi | giới tính |
|:-----:|:----:|:---------:|
| Alice | 20   |    Nữ     |
|  Bob  | 21   |    Nam    |


## Khối mã
- Khối mã với backticks
```java
public class A{
  public static void main(String [] args) {
     System.out.println("hello world!");
  }
}
```
- Khối mã với 4 khoảng trắng 
  public class A{
    public static void main(String [] args) {
       System.out.println("hello world!");
    }
  }

- Khối mã với hugo shortcode

{{< highlight html >}} <!doctype html>

<title>Example HTML5 Document</title>
  <p>Đây là một đoạn văn </p>

{{< /highlight >}}

## Danh sách 
### Danh sách không thứ tự

```
- mục 1
- mục 2
```

- mục 1
- mục 2

### Danh sách có thứ tự
```
1. mục 1
2. mục 2
```
1. mục 1
2. mục 2

## Các phần tử khác — abbr, sub, sup, kbd, mark

```html
<abbr title="Graphics Interchange Format">GIF</abbr> là một định dạng hình ảnh bitmap.

H<sub>2</sub>O

X<sup>n</sup> + Y<sup>n</sup> = Z<sup>n</sup>

Nhấn <kbd>CTRL</kbd>+<kbd>ALT</kbd>+<kbd>Delete</kbd> để kết thúc phiên làm việc.

Hầu hết <mark>kỳ nhông</mark> hoạt động về đêm, và săn côn trùng, giun và các sinh vật nhỏ khác.
```

<abbr title="Graphics Interchange Format">GIF</abbr> là một định dạng hình ảnh bitmap.

H<sub>2</sub>O

X<sup>n</sup> + Y<sup>n</sup> = Z<sup>n</sup>

Nhấn <kbd>CTRL</kbd>+<kbd>ALT</kbd>+<kbd>Delete</kbd> để kết thúc phiên làm việc.

Hầu hết <mark>kỳ nhông</mark> hoạt động về đêm, và săn côn trùng, giun và các sinh vật nhỏ khác.


## Công thức toán học

hỗ trợ Tex
- bật cho toàn bộ trong `hugo.toml`
```toml
[params]
  math = true
```
- cho từng file cụ thể 
```md
---
math: true
---
```

```md
- Toán học khối:
  $$
  \varphi = 1+\frac{1} {1+\frac{1} {1+\frac{1} {1+\cdots} } }
  $$
- Toán học inline:
  Đây là một đa thức inline: $5x^2 + 2y -7$.
```

- Toán học khối:

  $$
  \varphi = 1+\frac{1} {1+\frac{1} {1+\frac{1} {1+\cdots} } }
  $$

- Toán học inline:

  Đây là một đa thức inline: $5x^2 + 2y -7$.
