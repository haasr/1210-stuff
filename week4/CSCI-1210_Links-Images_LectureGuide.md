# CSCI 1210 — Links & Images: Lecture Guide

## 1. What Makes the Web the Web
- **Hyperlinks** are what make the web non-linear
- Before: top-to-bottom reading (like a book)
- With links: users jump around, follow a "breadcrumb trail"

---

## 2. The `<a>` Element
- Creates a hyperlink; content between `<a>` and `</a>` becomes clickable
- Default browser style: blue and underlined (overridable with CSS)
- Key attribute: `href` ("hypertext reference") — the destination address

**href can be:**
- Absolute URL (`https://...`) — for external sites
- Relative URL (`page.html`) — for your own site
- Page fragment (`#section-id`) — jumps within a page
- `mailto:` or `ftp:` — other protocols

---

## 3. Absolute vs. Relative URLs
| Type | When to Use | Example |
|------|-------------|---------|
| Absolute | Linking to another site | `href="https://example.com"` |
| Relative | Linking within your own site | `href="about.html"` |

**Golden Rule:** Relative for internal, absolute for external.

**Path navigation:**
- Same dir: `filename.html`
- Subdirectory: `folder/file.html` *(no leading slash!)*
- Up one level: `../file.html`
- Up two levels: `../../file.html`

---

## 4. Special Link Types
- **Fragments:** Give an element an `id`, then link with `href="#id"` — used for "back to top," TOCs, single-page nav
- **`target="_blank"`:** Opens link in a new tab — good for external links
- **`mailto:`:** Opens user's mail client — rarely used in modern dev

---

## 5. The `<img>` Element
- Self-closing inline element
- **Required:** `src` (path to image), `alt` (accessibility text)
- **Optional:** `title` (tooltip on hover)

**Writing good `alt` text:**
- Describe what the image actually shows
- Be concise; don't start with "image of…"
- Decorative images: use `alt=""`

---

## 6. Captions — `<figure>` & `<figcaption>`
```html
<figure>
  <img src="images/globe.jpg" alt="globe picture">
  <figcaption>Glass Globe</figcaption>
</figure>
```
- Semantic HTML — tells browser/screen readers image + caption belong together
- Better than wrapping in a `<div>`

---

## 7. Image Links
- Nest `<img>` inside `<a>` — the whole image becomes clickable
- Always include `alt` text; use `target="_blank"` for external links

---

## 8. Image Formats
| Format | Best For | Notes |
|--------|----------|-------|
| JPG/JPEG | Photos | Lossy compression; no transparency |
| PNG | Logos, icons, transparency | Lossless; larger files than JPG |
| GIF | Simple animations | Only 256 colors; not for photos |

---

## 9. Image Resolution & Optimization
- Web standard: **72 PPI** (print is 300 PPI — wasteful for web)
- File size is the #1 factor in page load time

**Page weight targets:**
- < 14 KB: "instant" zone (above-the-fold)
- 1–1.5 MB: ideal total
- < 3 MB: max recommended

**Three optimization techniques:**
1. **Crop** — remove unimportant areas
2. **Resize** — reduce dimensions to actual display size
3. **Compress** — JPEG quality 75–85 is often indistinguishable from 100

**Tools:** GIMP (free) or Adobe Photoshop (campus labs)

---

## 10. The Browser Cache
- Browser stores local copies of downloaded files
- Use the **same file path** for logos/repeated assets — downloaded once, cached for all pages

---

## 11. Web Design Lifecycle: Users & Requirements

### Targeted Users
- Every site has a targeted set of users — designing for everyone = designing for no one
- Info sources: marketing dept, surveys, existing site analytics

### User Personas
- A **persona** = description of a hypothetical user (goals, interests, tech comfort, fears)
- Characteristics: age, education, occupation, experience level, devices used

### Requirements
- **Specific:** explicit functional/design demands from the client
- **General:** inferred from user knowledge (e.g., older audience → larger text)
- Designers **gather** requirements; they don't determine them
- Conflicting requirements → bring to the client to resolve

**Elicitation techniques:** interviews, brainstorming, storyboards, role-playing, prototyping

---

## Quiz Answers (for reference)
1. `<a>` — creates a hyperlink
2. Blue and underlined — default link style
3. `src` & `alt` — required `<img>` attributes
4. True — images can be used as links
5. `.gif` or `.png` — support transparency
6. False — designers *gather*, not determine, requirements
7. False — site mission ≠ org mission statement
8. All of the above — personas, surveys, marketing dept
9. All of the above — age, gender, education, occupation, hobbies, experience, goals, devices
10. Opens the link in a new tab
