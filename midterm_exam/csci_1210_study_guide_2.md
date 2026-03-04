# CSCI 1210 — Essentials of Web Development Study Guide
### Midterm Review

---

## Table of Contents
1. [HTML Fundamentals](#1-html-fundamentals)
2. [URLs — Absolute vs. Relative](#2-urls--absolute-vs-relative)
3. [CSS Selectors, Properties & Values](#3-css-selectors-properties--values)
4. [CSS Color Notation](#4-css-color-notation)
5. [CSS Specificity & the Cascade](#5-css-specificity--the-cascade)
6. [Applying CSS to a Document](#6-applying-css-to-a-document)
7. [Block vs. Inline Elements](#7-block-vs-inline-elements)
8. [HTML Attributes](#8-html-attributes)
9. [Images & File Formats](#9-images--file-formats)
10. [**The Box Model**](#10-the-box-model)
11. [**Layout: Float**](#11-layout-float)
12. [**Layout: Position (relative, absolute, fixed)**](#12-layout-position-relative-absolute-fixed)
13. [Web Design Principles & Gestalt](#13-web-design-principles--gestalt)
14. [Site Planning & User Profiles](#14-site-planning--user-profiles)
15. [Debugging & Validation](#15-debugging--validation)
16. [Key Terminology Glossary](#16-key-terminology-glossary)

---

## 1. HTML Fundamentals

### The Three Main Elements of an HTML Document

Every valid HTML page is built from three nested elements:

```html
<!DOCTYPE html>
<html>
  <head>
    <!-- metadata, title, linked stylesheets -->
  </head>
  <body>
    <!-- visible page content -->
  </body>
</html>
```

| Element | Purpose |
|---|---|
| `<html>` | Root wrapper for the entire document |
| `<head>` | Contains metadata (title, CSS links, charset, etc.) — not visible on the page |
| `<body>` | Everything the visitor sees in the browser |

### Common Structural & Semantic Elements

| Element | Type | Purpose |
|---|---|---|
| `<h1>`–`<h6>` | Block | Headings |
| `<p>` | Block | Paragraph |
| `<div>` | Block | Generic container / chunk of content |
| `<span>` | Inline | Generic inline wrapper |
| `<ul>` / `<ol>` | Block | Unordered / Ordered list |
| `<li>` | Block | List item |
| `<a href="...">` | Inline | Hyperlink |
| `<img src="..." alt="...">` | Inline | Image |
| `<figure>` / `<figcaption>` | Block | Image with caption |
| `<blockquote>` | Block | Indented quotation |
| `<strong>` | Inline | Bold (semantic importance) |
| `<hr>` | Block | Horizontal rule (dividing line) |
| `<br>` | Inline | Line break (no closing tag) |

### ✏️ Practice: Spot the Errors

Look at the code below and identify **all errors** before reading the answer.

```html
<ul>
  <li><a href="index.html>HOME</a></li>
  <li><a href="about.html">ABOUT</a></li>
  <li><a href="pics.html">PICTURES</a></li>
  <li><a href="contact.html">CONTACT</a><li>
</ul>
```

<details>
<summary>▶ Reveal Errors</summary>

1. `href="index.html>HOME"` — the closing quote `"` after `index.html` is missing; the `>` is being swallowed into the attribute value.
2. `</li>` on the last item is written as `<li>` — it's missing the forward slash, so it's an opening tag instead of a closing tag.

</details>

---

### ✏️ Practice: Which `<figure>` code is most correct?

The goal is to display an image with a caption. Evaluate each option:

**Option A**
```html
<figure>
  <img src="images/chip.jpg" alt="Intel i9 Chip">
  <figcaption>Intel i9 Microprocessor</figcaption>
</figure>
```

**Option B** *(uses `<p>` instead of `<figure>`)*
```html
<p>
  <img src="images/chip.jpg" alt="Intel i9 Chip">
  <p>Intel i9 <br> Microprocessor</p>
</p>
```

**Option C** *(missing `alt` attribute)*
```html
<figure>
  <img src="images/chip.jpg">
  <figcaption>Intel i9 Microprocessor</figcaption>
</figure>
```

<details>
<summary>▶ Which is best and why?</summary>

**Option A** is the most correct:
- Uses semantic `<figure>` + `<figcaption>` pairing ✓
- Includes the required `alt` attribute ✓
- Nesting is valid ✓

Option B is invalid HTML (`<p>` cannot contain another block-level `<p>`).  
Option C is missing the required `alt` attribute (accessibility fail).

</details>

---

## 2. URLs — Absolute vs. Relative

| Type | Definition | Example |
|---|---|---|
| **Absolute** | Full address including protocol | `https://www.example.com/page.html` |
| **Relative** | Path from the current file's location | `../images/photo.jpg` |

> An absolute URL **always** begins with a protocol (`http://` or `https://`).

### Path Syntax

| Notation | Meaning |
|---|---|
| `images/photo.jpg` | `images` folder inside the **current** folder |
| `../images/photo.jpg` | Go **up one** folder, then into `images` |
| `/images/photo.jpg` | From the **site root** |

### ✏️ Practice: Correct Image Path

Given the folder structure below, you are editing `index.html`. Which `src` is correct to display `linux.png`?

```
ramseyjw/
├── index.html
└── images/
    └── linux.png
```

**A)** `src="../images/linux.png"`  
**B)** `src="images/linux.png"`  
**C)** `src="images/linux.png"` *(no alt)*  
**D)** `src="images/linux.png" alt="Tux the Penguin"`

<details>
<summary>▶ Answer</summary>

**D** — both a correct relative `src` path *and* the required `alt` attribute are needed for valid, accessible HTML.

</details>

---

## 3. CSS Selectors, Properties & Values

### Anatomy of a CSS Rule

```css
h1 {
  color: red;           /* property: value */
  background-color: blue;
}
```

| Part | Example | Definition |
|---|---|---|
| **Selector** | `h1` | *Who* gets styled |
| **Property** | `color` | *What* is being changed |
| **Value** | `red` | *How* it is changed |
| **Declaration** | `color: red;` | One property–value pair |
| **Rule / Rule Set** | The whole block | Selector + all declarations |

### Selector Types

| Selector | Syntax | Targets |
|---|---|---|
| Element | `p { }` | All `<p>` elements |
| Class | `.special { }` | Any element with `class="special"` |
| ID | `#header { }` | The element with `id="header"` |
| Contextual (grouped) | `h1, h2 { }` | Both `h1` and `h2` elements |
| Descendant | `nav a { }` | `<a>` tags *inside* a `<nav>` |

### Applying a Class in HTML

```css
/* CSS */
.highlight {
  background-color: yellow;
  font-weight: bold;
}
```

```html
<!-- HTML -->
<p class="highlight">This text will be yellow and bold.</p>
```

### ✏️ Practice: Match the CSS to the Visual

Below is a rendered paragraph. Identify which CSS class definition produced it.

```html
<p class="exam">Sed inceptos erat eleifend tempus...</p>
```

The paragraph displays with: **blue italic text**, a **blue border**, centered horizontally with **padding**, and a **text indent**.

**Option A**
```css
p.exam {
  width: 300px; border: 1px solid blue;
  margin-left: 25px; color: blue;
  padding: 20px; font-style: italic;
}
```
**Option B**
```css
p.exam {
  width: 300px; border: 1px solid blue;
  margin-left: 25px; color: blue;
  font-style: italic; text-indent: 20px;
}
```

<details>
<summary>▶ Answer</summary>

**Option B** — The display shows a text indent (first line is indented) but the paragraph is not padded symmetrically on all sides. `text-indent` is the right property; `padding: 20px` would add space around all four edges, not just indent the first line.

</details>

---

## 4. CSS Color Notation

CSS supports four ways to specify color:

| Notation | Example | Notes |
|---|---|---|
| Named | `color: red;` | ~140 named colors |
| Hex | `color: #FF0000;` | `#RRGGBB` — 00 = none, FF = full |
| RGB | `color: rgb(255, 0, 0);` | 0–255 per channel |
| RGBA | `color: rgba(255, 0, 0, 0.5);` | Adds alpha (transparency 0–1) |

### Hex Color Breakdown

```
#FF0000
  ^^      = Red channel (FF = 255 = full red)
    ^^    = Green channel (00 = 0)
      ^^  = Blue channel (00 = 0)
```

### ✏️ Practice: Which produce RED?

Circle all that display red text:

- A) `color: #0000FF;`
- B) `rgba(0, 255, 0, .5)`
- C) `color: rgb(255, 0, 0);`
- D) `color: #FF0000;`
- E) `color: rbg(0, 255, 0)` *(note the typo)*
- F) `color: #00FF00;`

<details>
<summary>▶ Answer</summary>

**C and D** are correct.
- A = blue (#0000FF)
- B = semi-transparent green (also missing the `color:` property name)
- E = invalid — `rbg` is misspelled
- F = green (#00FF00)

</details>

---

## 5. CSS Specificity & the Cascade

When multiple CSS rules target the same element, the browser uses **specificity** to decide which wins.

### Specificity Hierarchy (lowest → highest)

```
External stylesheet  <  Internal <style> tag  <  Inline style=""
```

| Selector Type | Specificity Weight |
|---|---|
| Element (`p`, `h1`) | Low |
| Class (`.note`) | Medium |
| ID (`#header`) | High |
| Inline (`style="..."`) | Highest |

### ✏️ Practice Question

Given:
- Internal stylesheet rule: `p { font-size: 12px; }`
- Inline style on the element: `style="font-size: 14px;"`

What font size will the paragraph display?

<details>
<summary>▶ Answer</summary>

**14px** — Inline styles always override stylesheet rules (external or internal) because they have the highest specificity.

</details>

---

## 6. Applying CSS to a Document

There are **three** ways to apply CSS. Know them all.

### 1. External CSS *(most common / best practice)*
```html
<head>
  <link rel="stylesheet" href="styles/main.css">
</head>
```

### 2. Internal (Embedded) CSS
```html
<head>
  <style>
    body { background-color: #f0f0f0; }
    h1   { color: navy; }
  </style>
</head>
```

### 3. Inline CSS *(use sparingly)*
```html
<p style="color: green; font-weight: bold;">Hello!</p>
```

---

## 7. Block vs. Inline Elements

| Characteristic | Block Element | Inline Element |
|---|---|---|
| Starts a new line? | ✅ Yes | ❌ No |
| Takes full width? | ✅ By default | ❌ Only as wide as content |
| Can set width/height? | ✅ Yes | ❌ Generally no |
| Examples | `<div>`, `<p>`, `<h1>`, `<ul>`, `<li>`, `<blockquote>` | `<span>`, `<a>`, `<img>`, `<strong>`, `<br>` |

---

## 8. HTML Attributes

An **attribute** provides additional information about an element. It appears *inside the opening tag* as a `name="value"` pair.

```html
<a href="about.html" class="nav-link" id="about-btn">About</a>
```

In the tag above: `href`, `class`, and `id` are all **attributes**. `"about.html"`, `"nav-link"`, and `"about-btn"` are their **values**.

### ✏️ Practice: Identify the Attributes

```html
<p class="note" style="width:400px; height:200px; background: #0000AF; border: 1px solid #999999;" id="sidenote">
```

Which of the following are **attributes**?

`width` / `class` / `400px` / `#999` / `id` / `style` / `border` / `background`

<details>
<summary>▶ Answer</summary>

**Attributes:** `class`, `id`, `style`

`width`, `border`, `background` are CSS *properties* (inside the style attribute's value).  
`400px` and `#999` are CSS *values*.

</details>

---

## 9. Images & File Formats

### Common Web Image Formats

| Format | Best For | Transparency? | Notes |
|---|---|---|---|
| `.jpg` / `.jpeg` | Photographs | ❌ No | Lossy compression; small file size |
| `.png` | Logos, screenshots, graphics | ✅ Yes | Lossless; larger than JPG |
| `.gif` | Simple animations, icons | ✅ (1-bit) | Limited to 256 colors |
| `.svg` | Icons, logos (scalable) | ✅ Yes | Vector-based; infinitely scalable |
| `.webp` | General purpose (modern) | ✅ Yes | Excellent compression |

### Why Optimize Images?
- Larger images = **longer download times** = poor user experience
- Page load speed affects **SEO rankings**
- Mobile users on slower connections are disproportionately impacted

### Correct `<img>` Syntax

```html
<!-- ✅ Correct — includes src and alt -->
<img src="images/photo.jpg" alt="Description of image">

<!-- ❌ Wrong — alt is missing its closing quote, breaking the tag -->
<img src="images/me.png alt="my image">
```

---

## 10. The Box Model

Every HTML element is treated as a rectangular **box**. The box model describes the four layers that surround an element's content.

```
┌──────────────────────────────────┐
│             MARGIN               │  ← Transparent space outside border
│  ┌────────────────────────────┐  │
│  │           BORDER           │  │  ← Optional visible line
│  │  ┌──────────────────────┐  │  │
│  │  │       PADDING        │  │  │  ← Space between border & content
│  │  │  ┌────────────────┐  │  │  │
│  │  │  │    CONTENT     │  │  │  │  ← The actual text/image
│  │  │  └────────────────┘  │  │  │
│  │  └──────────────────────┘  │  │
│  └────────────────────────────┘  │
└──────────────────────────────────┘
```

### Key Properties

```css
.box {
  width: 300px;          /* content width */
  padding: 20px;         /* inside: content → border */
  border: 2px solid navy;
  margin: 30px auto;     /* outside: border → neighboring elements */
                         /* auto on left/right = horizontally centered */
}
```

### Box-Sizing

By default (`content-box`), `width` only applies to the content. Padding and border are **added on top**.

```css
/* content-box (default): total width = 300 + 20 + 20 + 2 + 2 = 344px */
.default { width: 300px; padding: 20px; border: 2px solid black; }

/* border-box: total width = exactly 300px (padding/border are subtracted inside) */
.better  { box-sizing: border-box; width: 300px; padding: 20px; border: 2px solid black; }
```

### ✏️ Practice: Calculate the Total Width

A `<div>` has these styles:
```css
.card {
  width: 250px;
  padding: 15px;
  border: 3px solid black;
  margin: 20px;
  box-sizing: content-box;
}
```

What is the element's **total rendered width** (including margin)?

<details>
<summary>▶ Answer</summary>

`margin-left(20) + border-left(3) + padding-left(15) + content(250) + padding-right(15) + border-right(3) + margin-right(20)` = **326px** total space taken up in the layout.

</details>

### ✏️ Practice: Match the Visual to the Box Model Code

Look at the rendered box below and select the CSS that produced it.

> A blue box is displayed, centered on the page, with noticeable space **inside** the border between the text and the edge, and equal space **outside** the box on all sides.

**Option A**
```css
.info-box {
  width: 400px;
  margin: 0;
  padding: 0;
  border: 2px solid blue;
}
```

**Option B**
```css
.info-box {
  width: 400px;
  margin: 30px auto;
  padding: 20px;
  border: 2px solid blue;
}
```

**Option C**
```css
.info-box {
  width: 400px;
  margin: 30px auto;
  padding: 0;
  border: 2px solid blue;
}
```

<details>
<summary>▶ Answer</summary>

**Option B** — `margin: 30px auto` centers the box horizontally and adds outer space; `padding: 20px` provides inner breathing room between text and border.

</details>

---

## 11. Layout: Float

`float` pulls an element to the left or right, allowing other content (like text) to **wrap around it**.

```css
img.left  { float: left;  margin: 0 15px 10px 0; }
img.right { float: right; margin: 0 0 10px 15px; }
```

### How Float Works

```
┌──────────────────────────────────────────┐
│  ┌───────┐  Text wraps around the image  │
│  │ IMAGE │  on whichever side is free.   │
│  │ float │  The image is "pulled" to     │
│  │ :left │  the left of the container.   │
│  └───────┘                               │
│  More text continues here after the      │
│  image if there is enough of it...       │
└──────────────────────────────────────────┘
```

### Clearing a Float

After a floated element, you often need to **clear** to prevent the next element from wrapping.

```css
.clearfix::after {
  content: "";
  display: block;
  clear: both;
}
```

### ✏️ Practice: Image Float

Which CSS property/value would produce this layout?

```
┌─────────────────────────────────────────┐
│         Lorem Ipsum Heading             │
│  ┌──────┐                               │
│  │ img  │  Lorem ipsum dolor sit amet,  │
│  │      │  consectetur adipiscing elit. │
│  └──────┘  Sed ut perspiciatis...       │
└─────────────────────────────────────────┘
```

**A)** `text-align: left;`  
**B)** `float: left;`  
**C)** `float: right;`  
**D)** `margin: auto;`

<details>
<summary>▶ Answer</summary>

**B)** `float: left;` — The image is on the left side with text wrapping to its right.

</details>

### ✏️ Practice: Spot the Invalid Float Value

```css
.img-centered {
  display: block;
  float: center;
  border: 1px solid #0000AA;
}
```

What's wrong with this code?

<details>
<summary>▶ Answer</summary>

`float: center;` is **not a valid value**. Float only accepts `left`, `right`, `none`, or `inherit`. To center a block-level image, use `margin: 0 auto;` with `display: block;` instead.

</details>

---

## 12. Layout: Position (relative, absolute, fixed)

The `position` property controls how an element is placed in the document flow.

### Position Values

| Value | In Normal Flow? | Offset From | Common Use |
|---|---|---|---|
| `static` | ✅ Yes (default) | N/A | Default |
| `relative` | ✅ Yes | Its **own original position** | Slight nudges; creates positioning context |
| `absolute` | ❌ No | Nearest **positioned ancestor** | Tooltips, overlays, badges |
| `fixed` | ❌ No | The **viewport** (browser window) | Sticky headers, floating buttons |
| `sticky` | Hybrid | Scrolls until threshold, then fixed | Nav bars that stick on scroll |

### Relative Positioning

The element stays in normal flow but is **visually offset** from where it would have been.

```css
.nudged {
  position: relative;
  top: 10px;   /* move 10px DOWN from original position */
  left: 20px;  /* move 20px RIGHT from original position */
}
```

```
Normal flow position → [element was here]
Rendered position    →     [element appears here, shifted]
```

### Absolute Positioning

The element is removed from normal flow. It positions itself relative to the **nearest ancestor with `position: relative` (or absolute/fixed)**. If none exists, it's relative to the `<body>`.

```css
.container {
  position: relative; /* establishes positioning context */
  width: 300px;
  height: 200px;
  border: 1px solid #ccc;
}

.badge {
  position: absolute;
  top: 10px;
  right: 10px;
  background: red;
  color: white;
  padding: 4px 8px;
}
```

```
┌─────────────────────────────┐
│ .container (relative)  [badge]  ← .badge (absolute, top:10px right:10px)
│                              │
│  Normal content here...      │
└─────────────────────────────┘
```

### ✏️ Practice: Which position value?

You want to place a small "NEW" label in the **top-right corner** of a product card, regardless of the card's content. The card has `position: relative`. What `position` value do you use on the label?

<details>
<summary>▶ Answer</summary>

`position: absolute;` — combined with `top: 0; right: 0;`, the label will anchor itself to the corner of the nearest positioned ancestor (the card).

</details>

### ✏️ Practice: Relative vs. Absolute

Given this code, describe what you would see:

```css
.parent {
  position: relative;
  width: 200px; height: 200px;
  background: lightblue;
}

.child-relative {
  position: relative;
  top: 20px; left: 20px;
  width: 80px; height: 80px;
  background: coral;
}

.child-absolute {
  position: absolute;
  top: 20px; right: 20px;
  width: 80px; height: 80px;
  background: gold;
}
```

```html
<div class="parent">
  <div class="child-relative">A</div>
  <div class="child-absolute">B</div>
</div>
```

<details>
<summary>▶ Answer</summary>

- **Box A (coral):** Appears in normal flow, shifted 20px down and 20px right from where it would naturally be. Other elements flow around its original space.
- **Box B (gold):** Removed from flow, pinned 20px from the top and 20px from the right edge of the light-blue `.parent` container.

</details>

### ✏️ Practice: Spot the Invalid Value

```css
.img-centered {
  display: block;
  position: center;
  border: 1px solid #0000AA;
}
```

What is wrong?

<details>
<summary>▶ Answer</summary>

`position: center;` is **not a valid CSS value** for the `position` property. Valid values are `static`, `relative`, `absolute`, `fixed`, and `sticky`. To center a block element, use `margin: 0 auto;`.

</details>

---

## 13. Web Design Principles & Gestalt

### Gestalt Principles in Web Design

| Principle | Description |
|---|---|
| **Proximity** | Elements close together are perceived as related |
| **Similarity** | Elements that look alike are grouped mentally |
| **Continuation** | The eye is guided along a line, curve, or path through the composition |
| **Closure** | The mind fills in gaps to complete a shape |
| **Figure/Ground** | Distinguishing an object from its background |

> **Continuation example:** A long corridor, road, or railway track that leads the eye deep into the image — the viewer's gaze follows the lines naturally toward a vanishing point.

### ✏️ Practice: Identify the Principle

Which Gestalt principle is demonstrated when a group of navigation buttons all share the same shape, color, and font — visually telling users they all do the same *type* of thing?

<details>
<summary>▶ Answer</summary>

**Similarity** — consistent visual treatment communicates that elements belong to the same category or have the same function.

</details>

---

## 14. Site Planning & User Profiles

### What is a Profile?
A **profile** (sometimes called a *persona*) is a hypothetical representation of a typical user of a web site. It is used during the design process to keep the team focused on the real audience.

A profile typically includes:
- Age range
- Technical skill level
- Goals / what they're trying to accomplish
- Device & browsing context
- Education level

> Profiles do **not** include personally identifiable information (SSN, phone numbers, etc.).

### Designers vs. Developers
A common exam topic: who does what?

| Role | Primary Responsibility |
|---|---|
| **Designer** | Visual look, user experience, layout mockups |
| **Developer** | Building and coding the actual site |
| **Client** | Defines business goals and site requirements |

> Site **requirements** are determined by the **client** (not the designer).

### Well-Designed Sites Have…
- A clearly **targeted audience**
- A well-defined **mission / purpose**
- Simple, intuitive **navigation**
- Accessible, optimized content

---

## 15. Debugging & Validation

### Reading Error Messages

When a CSS validator returns:
```
URI: http://example.com/css/styles.css
Line 94 — .img-centered — Value Error: position center
```

- The error is in `styles.css` (not the HTML file)
- The problem is on **line 94** of that CSS file
- `.img-centered` is the selector with the bad value

### HTML Validation Tips
- Every opening tag needs a closing tag (or self-closes: `<br>`, `<img>`, `<hr>`)
- All attribute values must be wrapped in matching quotes (`"` or `'`)
- Elements must be properly nested — don't overlap tags

---

## 16. Key Terminology Glossary

| Term | Definition |
|---|---|
| `<!DOCTYPE html>` | Declaration that tells the browser this is an HTML5 document |
| **Attribute** | Extra information inside an opening tag, written as `name="value"` |
| **Selector** | The part of a CSS rule that identifies which element(s) to style |
| **Property** | The CSS characteristic being changed (e.g., `color`, `font-size`) |
| **Value** | The setting assigned to a CSS property |
| **Specificity** | The algorithm browsers use to decide which CSS rule wins a conflict |
| **DNS** | Domain Name System — maps human-readable URLs to IP addresses |
| **HTTP** | HyperText Transfer Protocol — how browsers and servers communicate |
| **FTP** | File Transfer Protocol — used to copy files between computers |
| **URL** | Uniform Resource Locator — unique address of a resource on the web |
| **W3C** | World Wide Web Consortium — organization that sets web standards |
| **Profile / Persona** | Hypothetical "typical user" used in design planning |
| **Box Model** | The four-layer model (content, padding, border, margin) around every element |
| **Float** | CSS property that pulls an element left or right, allowing text to wrap |
| **Absolute positioning** | Removes element from flow; placed relative to nearest positioned ancestor |
| **Relative positioning** | Element stays in flow but is visually offset from its natural position |

---

*Study Tip: For every concept, try to write the code from memory, then validate it in a browser. Seeing the visual output reinforces what the syntax actually does.*
