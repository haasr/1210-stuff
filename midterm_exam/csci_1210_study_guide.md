# CSCI 1210 — Midterm Study Guide

Use this guide to review the key concepts covered on the midterm. My recommendation: don't attempt to memorize the HTML and CSS by just looking at it. For example, make some small HTML files and try to apply CSS rules to do things like set alt text on an image, make it float left, center it, etc.
---

## 1. HTML Fundamentals

### Document Structure
Every valid HTML document has three required elements that wrap all content:

```html
<!DOCTYPE html>
<html>
  <head>
    <!-- Meta-data: title, linked stylesheets, scripts, etc. -->
  </head>
  <body>
    <!-- All visible page content goes here -->
  </body>
</html>
```

| Element | Purpose |
|---|---|
| `<!DOCTYPE html>` | Tells the browser this is an HTML5 document |
| `<html>` | Root element — wraps the entire document |
| `<head>` | Contains meta-data (not displayed in the browser) |
| `<body>` | Contains all visible page content |

### Attributes
An **attribute** is extra information added to an HTML element inside its opening tag. Attributes have a **name** and a **value**.

```html
<p class="note" id="intro" style="color: blue;">
```

In this example, `class`, `id`, and `style` are **attributes**. `"note"`, `"intro"`, and `"color: blue;"` are their **values**. Things like `color` and `border` inside a `style` attribute are CSS properties, not HTML attributes.

**Common attributes to know:**

| Attribute | Used On | Purpose |
|---|---|---|
| `src` | `<img>` | Path to the image file |
| `alt` | `<img>` | Fallback text describing the image |
| `href` | `<a>` | URL the link points to |
| `class` | Any element | Assigns a CSS class |
| `id` | Any element | Assigns a unique CSS identifier |
| `style` | Any element | Applies inline CSS |

### Common Elements to Know

| Element | Type | Description |
|---|---|---|
| `<h1>`–`<h6>` | Block | Headings |
| `<p>` | Block | Paragraph |
| `<div>` | Block | Generic container for grouping content |
| `<ul>` / `<ol>` | Block | Unordered / ordered list |
| `<li>` | Block | List item |
| `<a>` | Inline | Hyperlink |
| `<img>` | Inline | Image |
| `<strong>` | Inline | Bold text (semantic) |
| `<hr>` | Block | Horizontal rule (dividing line) |
| `<br>` | Inline | Line break |
| `<blockquote>` | Block | Indented block quotation |
| `<figure>` / `<figcaption>` | Block | Image with caption |
| `<q>` | Inline | Short inline quotation (adds quotes automatically) |

### Block vs. Inline Elements
- **Block elements** start on a new line and create whitespace above and below their content. Examples: `<div>`, `<p>`, `<h1>`, `<blockquote>`.
- **Inline elements** do not interrupt the flow of the document — they sit within the surrounding text. Examples: `<a>`, `<img>`, `<strong>`, `<q>`.

---

## 2. HTML Syntax & Common Errors

Look out for common errors and typos in HTML:

### Missing or Mismatched Quotes
```html
<!-- ❌ Error: closing quote missing on src attribute -->
<img src="images/me.png alt="my image">

<!-- ✅ Correct -->
<img src="images/me.png" alt="my image">
```

### Missing Closing Tags
```html
<!-- ❌ Error: <li> is not closed (should be </li>) -->
<li><a href="contact.html">CONTACT</a><li>

<!-- ✅ Correct -->
<li><a href="contact.html">CONTACT</a></li>
```

### Wrong Attribute Name
```html
<!-- ❌ Error: images use src, not href -->
<img href="images/linux.png" alt="Tux">

<!-- ✅ Correct -->
<img src="images/linux.png" alt="Tux">
```

### Nested Paragraph Tags
`<p>` tags cannot contain other `<p>` tags or most other block-level elements. This is invalid:
```html
<!-- ❌ Invalid nesting -->
<p>
  <img src="chip.jpg">
  <p>Caption text</p>
</p>
```

### The `alt` Attribute
Always include `alt` on `<img>` elements. Omitting it isn't a syntax crash, but it is considered poor/incomplete code and will cost you points.

---

## 3. URLs and File Paths

### Absolute vs. Relative URLs
- An **absolute URL** includes the full protocol and domain: `http://www.example.com/page.html`
- A **relative URL** is a path relative to the current file: `images/photo.jpg` or `../index.html`

> A URL that starts with `http://` or `https://` is always absolute. A URL that starts with a folder name or `../` is always relative.

### Navigating Directories

| Path | Meaning |
|---|---|
| `images/photo.jpg` | Go *into* the `images` subfolder |
| `../images/photo.jpg` | Go *up* one level, then into `images` |
| `../../file.html` | Go *up* two levels |

**Exam tip:** If `index.html` and the `images` folder are in the same directory, the correct path is `images/linux.png` — no `../` needed.

---

## 4. CSS Fundamentals

### CSS Terminology
```css
h1 {
  color: red;
  background-color: blue;
}
```

| Term | Example | Definition |
|---|---|---|
| **Selector** | `h1` | Targets which HTML elements to style |
| **Property** | `color` | The style characteristic being set |
| **Value** | `red` | The setting applied to the property |
| **Declaration** | `color: red;` | One property-value pair |
| **Rule** | The whole block | Selector + all its declarations |

### Three Ways to Apply CSS

| Method | Syntax | Where it lives |
|---|---|---|
| **Inline** | `<p style="color:red;">` | Inside an HTML element's tag |
| **Embedded (Internal)** | `<style> p { color:red; } </style>` | Inside `<head>` in the HTML file |
| **External** | `<link rel="stylesheet" href="style.css">` | In a separate `.css` file |

### CSS Specificity (Cascade Order)
When conflicting rules exist, **inline CSS always wins** over embedded/external CSS. This is called specificity.

```
Inline style  >  Internal stylesheet  >  External stylesheet
```

So if `style="font-size: 14px;"` is on the element, and the stylesheet says `p { font-size: 12px; }`, the result is **14px**.

### Selectors

| Selector | Syntax | Targets |
|---|---|---|
| Element | `p { }` | All `<p>` elements |
| Class | `.special { }` | All elements with `class="special"` |
| ID | `#header { }` | The element with `id="header"` |
| Grouped | `h1, h2 { }` | Both `h1` and `h2` elements |
| Class on element | `p.exam { }` | Only `<p>` elements with `class="exam"` |

To apply a class style to an HTML element:
```html
<p class="special">This text gets the .special styles.</p>
```
Note: use `class=`, not `id=`, `context=`, or `style=`.

### Useful CSS Properties

| Property | Example | Effect |
|---|---|---|
| `color` | `color: blue;` | Text color |
| `background-color` | `background-color: #000;` | Background fill |
| `font-style` | `font-style: italic;` | Italic text |
| `font-size` | `font-size: 14px;` | Text size |
| `border` | `border: 1px solid blue;` | Box border |
| `margin` | `margin: 10px auto;` | Space outside the element |
| `margin-left` | `margin-left: 25px;` | Left margin only |
| `padding` | `padding: 20px;` | Space inside the element |
| `text-indent` | `text-indent: 20px;` | Indent the first line of text |
| `width` | `width: 300px;` | Element width |
| `float` | `float: right;` | Float element left or right (text wraps) |
| `display: block` | `display: block;` | Make element behave as block |

### Centering an Image with CSS
There is no `float: center` or `position: center` in CSS. To center a block image, use `margin: auto`:

```css
.img-centered {
  display: block;
  margin: 10px auto;  /* top/bottom: 10px, left/right: auto = centered */
}
```

### Floating Images
To make text wrap around an image, use `float`:
```css
img {
  float: right;  /* image goes right, text wraps on the left */
}
```

---

## 5. Color in CSS

CSS colors can be written several ways. Know which values produce which colors.

| Format | Example | Notes |
|---|---|---|
| Named | `color: red;` | Easy to read; limited set of names |
| Hex | `color: #FF0000;` | Format is `#RRGGBB` (red, green, blue in hex) |
| RGB | `color: rgb(255, 0, 0);` | Values 0–255 per channel |
| RGBA | `color: rgba(255, 0, 0, 0.5);` | Like RGB + alpha (opacity) channel |

**Key hex values to memorize:**

| Color | Hex | RGB |
|---|---|---|
| Red | `#FF0000` | `rgb(255, 0, 0)` |
| Green | `#00FF00` | `rgb(0, 255, 0)` |
| Blue | `#0000FF` | `rgb(0, 0, 255)` |
| Black | `#000000` | `rgb(0, 0, 0)` |
| White | `#FFFFFF` | `rgb(255, 255, 255)` |

---

## 6. Images on the Web

### Image Formats

| Format | Best For | Transparency? | Notes |
|---|---|---|---|
| `.jpg` / `.jpeg` | Photographs | No | Lossy compression; small file size |
| `.png` | Graphics, logos, screenshots | Yes | Lossless; larger than jpg |
| `.gif` | Simple animations, icons | Yes (1-bit) | Limited to 256 colors |
| `.svg` | Scalable vector graphics | Yes | Resolution-independent |
| `.bmp`, `.tiff`, `.raw` | Not for web | — | Too large; avoid on websites |

### Why Optimize Images?
Large image files increase page load times, which **negatively impacts user experience**. This is the primary reason to optimize — not storage cost, not display size.

### Correct Image Code
```html
<!-- Always include both src and alt -->
<img src="images/photo.jpg" alt="Description of photo">

<!-- Image with caption — use figure/figcaption -->
<figure>
  <img src="images/chip.jpg" alt="Intel i9 Chip">
  <figcaption>Intel i9 Microprocessor</figcaption>
</figure>
```

---

## 7. Web Infrastructure & Protocols

| Term | Stands For | Purpose |
|---|---|---|
| **HTTP** | Hypertext Transfer Protocol | How browsers request and receive web pages from servers |
| **FTP** | File Transfer Protocol | Used to transfer files between computers |
| **DNS** | Domain Name System | Maps human-readable domain names (e.g., `google.com`) to IP addresses |
| **URL** | Uniform Resource Locator | The unique address of a resource on the Internet |
| **W3C** | World Wide Web Consortium | The organization that sets web standards |

---

## 8. Web Design Concepts

### User Profiles
A **profile** (or persona) is a hypothetical representation of a "typical" user of your site. It helps designers make decisions that serve real user needs. Profiles are *not* prototypes, wireframes, or color palettes.

### Identifying Target Users
Valid methods include: the client's marketing department, the client's existing website, surveys of the existing customer base — essentially, any legitimate research method. **All of the above** is usually the right answer.

### Valid User Characteristics
When building a user profile, relevant characteristics include: age, gender, technical skill, education level, occupation, goals, etc. Information like phone numbers or Social Security numbers is personal/sensitive data — not a design characteristic.

### Every Well-Designed Site Has...
A set of **targeted users** and a **well-defined mission**. Navigation should be simple, not complex. Color schemes should have sufficient contrast, not low contrast.

### Gestalt Design Principles
The exam covers **Continuation**: the idea of guiding the viewer's eye through an image using composition (e.g., leading lines, perspective). A photo looking down a long corridor or escalator tunnel is a classic example of continuation — your eye follows the lines naturally.

---

## 9. Reading Browser Error Messages

When a CSS validator or browser dev tool shows an error like:

```
URI: http://example.com/css/style.css
Line 94 — .img-centered — Value Error: position center
```

You should start debugging at **line 94 of the CSS file listed in the URI** — in this case, `temp.css`. The error message tells you exactly where the problem is.

---

## 10. HTML Comments

```html
<!-- This is an HTML comment -->
```

HTML comments use `<!-- ... -->`. Do not confuse with:
- CSS/JS comments: `/* ... */`
- Python/shell comments: `# ...`
- JavaScript line comments: `// ...`

---

## Quick-Reference Cheat Sheet

### "Does this have errors?" Checklist
- [ ] Are all attribute values wrapped in matching quotes?
- [ ] Does every opening tag have a closing tag (where required)?
- [ ] Are elements correctly nested (no block inside inline)?
- [ ] Does `<img>` use `src=` (not `href=`)?
- [ ] Does `<img>` include an `alt` attribute?
- [ ] Does `<a>` use `href=` for the link destination?

### CSS "Does this work?" Checklist
- [ ] Is `float: center` used? → **Invalid.** Use `margin: auto` instead.
- [ ] Is `position: center` used? → **Invalid.** Use `margin: auto` instead.
- [ ] Is a class applied with `class="name"`? → Correct. (`id=`, `context=`, or `style=` will not apply a class rule)
- [ ] Is the hex color RRGGBB order? → `#FF0000` = red, `#0000FF` = blue.

---

*Good luck on the exam!*
