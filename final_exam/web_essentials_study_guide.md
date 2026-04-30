# Essentials of Web Development — Study Guide
### Final Exam Prep | Practice Questions

---

## Section 1: Networking & the Web

**1. (1 pt)** What does DNS stand for, and what is its primary function?

- A) Dynamic Node System — assigns IP addresses to devices on a network
- B) Domain Name System — translates human-readable domain names to IP addresses
- C) Distributed Network Service — routes packets across the internet
- D) Domain Navigation Standard — maps URLs to physical file paths on a server

---

**2. (1 pt)** In the following URL, which part is the **domain**?

```
https://www.example.edu/courses/web101/index.html
```

- A) `https://`
- B) `www`
- C) `example.edu`
- D) `/courses/web101/index.html`

---

**3. (1 pt)** Which of the following is the **TLD** in this URL?

```
http://www.csci1710.net/labs/lab2/index.html
```

- A) `http://`
- B) `.net`
- C) `lab2`
- D) `.html`

---

**4. (1 pt)** What is a **protocol** in the context of computer networking?

- A) A type of web server software
- B) An established rule that governs communication between systems
- C) A human-readable address for a website
- D) The file path portion of a URL

---

**5. (1 pt)** If a user navigates to `http://www.mysite.com` with no filename specified, what will the browser typically look for first?

- A) `home.html`
- B) `default.html`
- C) `index.html`
- D) The browser will return an error with no filename present

---

## Section 2: HTML Structure & Elements

**6. (2 pts)** Which of the following statements accurately describe HTML? *(select all that apply)*

- A) It is a compiled language
- B) It uses markup to describe structure
- C) It is plain text
- D) It must be processed by a server before the browser can read it
- E) It describes the structure of a web page

---

**7. (1 pt)** Where is the correct place in an HTML document to link an external stylesheet?

- A) In the `<body>` section
- B) At the very end of the document, after `</body>`
- C) In the `<head>` section
- D) In the doctype declaration

---

**8. (1 pt)** Which tag is used to link an external CSS file to an HTML document?

- A) `<style>`
- B) `<a>`
- C) `<href>`
- D) `<link>`

---

**9. (1 pt)** What is the correct HTML5 doctype declaration?

- A) `<!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 5.0//EN">`
- B) `<!DOCTYPE HTML5>`
- C) `<!DOCTYPE html>`
- D) `<DOCTYPE html>`

---

**10. (1 pt)** How would you classify the `<em>` element?

- A) Block container
- B) Inline container
- C) Block standalone
- D) Inline standalone

---

**11. (1 pt)** Which HTML element is used to display a **horizontal rule** (a thematic break line) on the page?

- A) `<br>`
- B) `<hr>`
- C) `<line>`
- D) `<rule>`

---

**12. (1 pt)** Which element do you nest inside a `<figure>` to add a caption?

- A) `<cap>`
- B) `<caption>`
- C) `<figcap>`
- D) `<figcaption>`

---

**13. (1 pt)** An `<article>` element **must** always be nested inside a `<section>` element.

- A) True
- B) False

---

**14. (1 pt)** `div` elements are: *(select the best answer)*

- A) Inline elements used to style small runs of text
- B) Block-level container elements used to group related content
- C) Semantic elements introduced in HTML5
- D) Only valid inside a `<form>` element

---

**15. (1 pt)** In HTML5, which attribute makes an input field **required** before a form can be submitted?

- A) `validate`
- B) `placeholder`
- C) `required`
- D) `formvalidate`

---

**16. (2 pts)** What is the correct HTML to create a **text input** field in a form?

- A) `<textfield>`
- B) `<input type="textfield">`
- C) `<input type="text">`
- D) `<textinput type="text">`

---

**17. (1 pt)** Which HTML element creates a **numbered (ordered) list**?

- A) `<ul>`
- B) `<dl>`
- C) `<ol>`
- D) `<list>`

---

## Section 3: Tables

**18. (1 pt)** Which attribute do you add to a `<td>` tag to make a cell **span multiple columns**?

- A) `cellspan="n"`
- B) `rowspan="n"`
- C) `colspan="n"`
- D) `cellspanh="n"`

---

**19. (3 pts)** What are the basic table elements in HTML? *(select all that apply)*

- A) `<tc>`
- B) `<table>`
- C) `<row>`
- D) `<tr>`
- E) `<td>`
- F) `<column>`
- G) `<cell>`

---

**20. (1 pt)** Browsers render HTML tables in what fashion?

- A) Column by column
- B) Row by row
- C) Spanned cells first, then everything else
- D) Bottom to top

---

**21. (1 pt)** To make cell "A" span **3 rows** vertically in a table, which code would you use?

`[ Graphic placeholder — table diagram showing cell A spanning 3 rows ]`

- A) `<td colspan="3">A</td>`
- B) `<td rowspan="3">A</td>`
- C) `<td hspan="3">A</td>`
- D) `<td rowspan="2">A</td>`

---

## Section 4: CSS Fundamentals

**22. (3 pts)** Which of the following are basic components of a CSS rule? *(select all that apply)*

- A) selector
- B) property
- C) value
- D) charset
- E) `<script>`
- F) link

---

**23. (1 pt)** How do you define a CSS **class** named `highlight`?

- A) `#highlight { ... }`
- B) `*highlight { ... }`
- C) `.highlight { ... }`
- D) `highlight { ... }`

---

**24. (1 pt)** Which of the following is **not** a valid class or ID name in CSS?

- A) `_content`
- B) `contentTwo`
- C) `$content`
- D) `content2`

---

**25. (1 pt)** Which CSS property controls **text size**?

- A) `text-size`
- B) `font-style`
- C) `text-style`
- D) `font-size`

---

**26. (1 pt)** Which CSS property and value makes text **bold**?

- A) `text-style: bold;`
- B) `font-weight: bold;`
- C) `font: bold;`
- D) `style: bold;`

---

**27. (1 pt)** What is the **default value** of the CSS `position` property?

- A) `relative`
- B) `absolute`
- C) `fixed`
- D) `static`

---

**28. (1 pt)** The CSS `position: fixed` property will:

- A) Affix an element relative to its nearest positioned parent
- B) Affix an element to a specific place in the viewport, even when the page is scrolled
- C) Hide the element from view
- D) `fixed` is not a valid value for `position`

---

**29. (1 pt)** Using `position` properties carelessly can cause one element to **overlap** another unintentionally.

- A) True
- B) False

---

**30. (1 pt)** Which CSS rule will correctly **center a block-level element** horizontally in its container?

- A) `margin: 0 auto;`
- B) `text-align: center;`
- C) `align: center;`
- D) `display: center;`

---

**31. (3 pts)** What are valid CSS **units of measure**? *(select all that apply)*

- A) `px`
- B) `km`
- C) `em`
- D) `%`
- E) `lb`
- F) `dp`

---

**32. (1 pt)** How do you add a **background color** to all `<h2>` elements?

- A) `h2.all { background-color: #FFFFFF; }`
- B) `all.h2 { background-color: #FFFFFF; }`
- C) `h2 { background-color: #FFFFFF; }`
- D) `<h2 style="background-color:#FFFFFF;">`

---

**33. (1 pt)** It is possible to apply the same CSS rules to **multiple selectors** in a single declaration (e.g., `h1, h2 { color: blue; }`).

- A) True
- B) False

---

**34. (2 pts)** How do you select **all `<p>` elements inside a `<div>`** using CSS?

- A) `div, p`
- B) `div.p`
- C) `div + p`
- D) `div p`

---

**35. (1 pt)** Which CSS selector responds to **user interaction** (such as hovering over an element)?

- A) Classes
- B) IDs
- C) Pseudo-classes
- D) Contextual selectors

---

**36. (1 pt)** Which of the following correctly defines **pseudo-class** syntax for links?

- A) `a[p]link, a[p]visited { color: red; }`
- B) `a:link, a:visited { color: red; }`
- C) `a>link, a>visited { color: red; }`
- D) `a link, a visited { color: red; }`

---

**37. (1 pt)** Which pseudo-class would you use to style a link that has already been **visited**?

- A) `a:link`
- B) `#visited`
- C) `a:visited`
- D) `.visited`

---

**38. (1 pt)** A CSS **ID** selector can be applied to multiple elements on the same page.

- A) True
- B) False

---

**39. (1 pt)** In the following CSS snippet, what is `border` called?

`[ Graphic placeholder — screenshot of CSS rule with 'border' property highlighted ]`

- A) selector
- B) value
- C) property
- D) content

---

**40. (1 pt)** In the CSS Box Model, what does the **outermost layer** (surrounding the border) represent?

`[ Graphic placeholder — CSS Box Model diagram ]`

- A) Padding
- B) Content
- C) Border
- D) Margin

---

**41. (1 pt)** What does the `float` CSS property cause a block-level element to do?

- A) Display on top of other elements
- B) Center itself in its container
- C) Display on the left or right of its container with content wrapping around it
- D) Fix its position on the page during scrolling

---

**42. (1 pt)** If an image is floated right and you want the **next paragraph to appear below** the image (not wrapping around it), what would you apply to the paragraph?

- A) `float: left;`
- B) `clear: right;`
- C) `width: 100%;`
- D) `display: block;`

---

**43. (2 pts)** How do you insert a **comment** in a CSS file?

- A) `' this is a comment`
- B) `// this is a comment`
- C) `/* this is a comment */`
- D) `<!-- this is a comment -->`

---

**44. (1 pt)** Which HTML attribute is used to apply **inline CSS styles** to an element?

- A) `font`
- B) `styles`
- C) `class`
- D) `style`

---

**45. (1 pt)** In CSS, linking to many external resources (e.g., multiple Google Fonts) can negatively impact **page load time**.

- A) True
- B) False

---

## Section 5: Images & Media

**46. (1 pt)** Why is it important to **optimize images** for the web?

- A) Larger files always take up more display space, making layout harder
- B) Storage costs from ISPs make unoptimized images expensive
- C) Since JPEGs use compression, optimization is never necessary
- D) Larger file sizes increase download times and hurt user experience

---

**47. (1 pt)** The image below uses a black background with smooth color gradients and fine lines. Based on those characteristics, which format is most likely being used?

`[ Graphic placeholder — colorful spirograph-style image on black background ]`

- A) `.bmp`
- B) `.gif`
- C) `.png`
- D) `.jpg`

---

**48. (1 pt)** Images can be used as **hyperlinks** in HTML.

- A) True
- B) False

---

**49. (1 pt)** Which of the following CSS properties/values would cause an image to display along the **right side** of its container with text wrapping around it?

- A) `float: left;`
- B) `text-align: right;`
- C) `align: left;`
- D) `float: right;`

---

## Section 6: Web Design Principles

**50. (1 pt)** What do we call the psychological design theory that states *the whole is perceived as greater than the sum of its parts*?

- A) Functional Fixedness
- B) Mosaic
- C) Gestalt
- D) Information Architecture

---

**51. (1 pt)** The two images below are an example of which Gestalt principle?

`[ Graphic placeholder — figure-ground illusion (e.g., vase/faces) ]`

- A) Proximity
- B) Figure-ground
- C) Continuity
- D) Similarity

---

**52. (1 pt)** With regard to color selection, what is the **most important** consideration for web design?

- A) Hue
- B) Saturation
- C) Luminosity
- D) Contrast

---

**53. (2 pts)** Which of the following represent **best-practice design tips**? *(select all that apply)*

- A) Establish a visual hierarchy
- B) Use as many fonts as possible to maintain interest
- C) Keep important content "above the fold"
- D) Guide the user's eye through the page
- E) Listen to the customer / stakeholder

---

**54. (1 pt)** What are the two primary things users use to judge a website?

- A) Color and text
- B) Load time and pictures
- C) Content and usability
- D) Context and ubiquity

---

**55. (1 pt)** A web site's **usefulness** is best judged by its:

- A) Utility and understandability
- B) Usability and user-friendliness
- C) Utility and usability
- D) Understandability and uniformity

---

**56. (1 pt)** What is the term for the science of figuring out what a site should contain and how it should best be organized and presented?

- A) Page Layout
- B) Navbar Design
- C) Information Architecture
- D) Filesystem Navigation

---

**57. (1 pt)** Every well-designed website has a set of targeted users and:

- A) A needlessly complex navigation structure
- B) Included multimedia content
- C) A well-defined mission
- D) A low-contrast color scheme

---

**58. (1 pt)** Regardless of client preferences, all targeted user groups should be given **equal priority** in the overall design.

- A) True
- B) False

---

**59. (1 pt)** Who makes the **best test subjects** for usability testing of a website?

- A) Random members of the design team
- B) College students
- C) Anyone available
- D) Subjects who closely match the target user profiles

---

**60. (1 pt)** Testing should only be conducted when a site is **fully ready to launch**, to avoid invalidating results.

- A) True
- B) False

---

## Section 7: Accessibility

**61. (1 pt)** Approximately what percentage of Americans have some form of disability?

- A) 5%
- B) 33%
- C) 45%
- D) 20%

---

**62. (2 pts)** What are the **primary concerns** associated with web accessibility? *(select all that apply)*

- A) Visual impairment
- B) Motor impairment
- C) Hearing impairment
- D) Financial impairment

---

**63. (1 pt)** Which of the following is **not** part of the W3C Web Accessibility Initiative's recommendations?

- A) Image text alternatives (`alt` attribute)
- B) Keyboard access and visual focus
- C) Requiring all pages to have a video alternative
- D) Contrast ratio ("color contrast")

---

## Section 8: Miscellaneous / History

**64. (1 pt)** Who is credited with inventing the World Wide Web?

- A) Alan Turing
- B) Al Gore
- C) Linus Torvalds
- D) Tim Berners-Lee

---

**65. (1 pt)** Why is **indentation** used in HTML and CSS code?

- A) It is required by the HTML/CSS syntax
- B) HTML and CSS are whitespace-dependent languages
- C) It serves no functional purpose
- D) It makes code more readable and maintainable

---

**66. (1 pt)** Why is it good practice to include **comments** in your code? *(select the best answer)*

- A) So you can remember what a piece of code does
- B) So collaborators can understand your intent
- C) To make code more readable and maintainable
- D) All of the above

---

**67. (1 pt)** What does **FTP** stand for?

- A) File Transmission Practice
- B) First Translation Protocol
- C) Full Transfer Pack
- D) File Transfer Protocol

---

---

## Answer Key

| Q | Answer | Q | Answer | Q | Answer |
|---|--------|---|--------|---|--------|
| 1 | B | 25 | D | 49 | D |
| 2 | C | 26 | B | 50 | C |
| 3 | B | 27 | D | 51 | B |
| 4 | B | 28 | B | 52 | D |
| 5 | C | 29 | A | 53 | A, C, D, E |
| 6 | B, C, E | 30 | A | 54 | C |
| 7 | C | 31 | A, C, D | 55 | C |
| 8 | D | 32 | C | 56 | C |
| 9 | C | 33 | A | 57 | C |
| 10 | B | 34 | D | 58 | B |
| 11 | B | 35 | C | 59 | D |
| 12 | D | 36 | B | 60 | B |
| 13 | B | 37 | C | 61 | D |
| 14 | B | 38 | B | 62 | A, B, C |
| 15 | C | 39 | C | 63 | C |
| 16 | C | 40 | D | 64 | D |
| 17 | C | 41 | C | 65 | D |
| 18 | C | 42 | B | 66 | D |
| 19 | B, D, E | 43 | C | 67 | D |
| 20 | B | 44 | D | | |
| 21 | B | 45 | A | | |
| 22 | A, B, C | 46 | D | | |
| 23 | C | 47 | C | | |
| 24 | C | 48 | A | | |
