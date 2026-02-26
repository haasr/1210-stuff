# Getting Started with GitHub

## 1. Create Account and Install GitHub Desktop

1. Sign up for an account on github.com. Write down your credentials somewhere safe!
2. Download and install GitHub Desktop (https://desktop.github.com/download/)

## 2. Create a Tutorial Repository

1. In GitHub Desktop, click "Create a Tutorial Repository...". Notice that you are on the "main" branch. A branch is a dedicated channel or version of all your project code and files.
	- "main" would typically be where you would store your polished, production-ready code when working with a team.
	- You can have as many other branches as you'd like. There are many different branching strategies. One popular strategy in Agile-style software development teams is feature branching, in which every new feature has its own dedicated branch, that once ready, is merged into the main branch (and the feature branch can subsequently be pruned).
	- While branching strategies are important for large projects and enterprise projects, feel free to keep things very simple for now. Even if your team is working out of only a main branch, just getting in the habit of using a git repository to centralize all your code in one place already puts you in good standing for later classes (especially Software Engineering) or the classic issue in which your work was mysteriously deleted from your device.
2. Create a "New Branch" and make sure you've selected that branch so its name is listed under "Current Branch".
3. Follow along with the rest of the "Get started" instructions on the right-hand side.
	- Note that the "Open Editor" button requires you to have an editor like Visual Studio Code set as the default editor for markdown (\*.md) files.
	- Markdown is a really simple format -- think of it as lightweight HTML if you'd like (you can use HTML in markdown documents for more specific structure/styling) although pure Markdown (no HTML) doesn't use tags. It is basically designed to give you just enough formatting to be useful without taking your hands off the keyboard. This document was written in markdown using the Obsidian editor! See the `Markdown Quick Start Guide` at the bottom for more.
	- **Step 4** - Make a commit: Requires you to write a title and optional description in the bottom left corner and click the "Commit" button.
4. Note the last step in the GitHub Desktop tutorial is to submit a "Pull Request". What is that? It might make more sense to call it a "Merge Request" because it is a request to merge your work with the work in the "main" branch.
	- The idea is that someone like your lead developer and/or quality manager would review your code to make sure that (1) it does what it is supposed to and (2) it will not break any existing code or features when merged into main. If they have questions or request changes, they can comment on the pull request and wait for your response and/or corrections before choosing to confirm or close your pull request.
	- If you work with multiple branches, that is what you will need to do whenever you reach a small milestone (e.g., finish your first cut of a webpage and ensured it passes validation).
	- Keep in mind that using multiple branches like this means you always want to try to sync your branch with the main one so you don't encounter a *merge conflict*. This is why you may consider just working out of a "main" branch for now.

## 3. Create Repositories for Your Team

I recommend the Document Manager create either a separate repository for each project phase or define a folder structure in a single repository that keep your phases separate (e.g., phase1, phase2, and phase3 folders).

However you do it, you will want to have a consistent organization for your website at each phase. Something like:

```
phase1/
  index.html
  about.html
  static/
    css/       <-- Folder containing your main stylesheet &
	               any other external stylesheets
      main.css
    img/       <-- Images
    js/        <-- Scripts if you have any
```

This is not a mandated folder organization. Just an example. A consistent structure across phases means your team members will all have a predictable way of writing links, e.g.,

```
<head>
  <link href="static/css/main.css" rel="stylesheet" type="text/css">
</head>

<body>
  <img class="img-rounded dropshadow-light" src="static/img/about-us.png" alt="">
</body>
```

### Invite Your Team Members

The Document Manager will need to invite everyone to each repository by navigating to the repository through a web browser and going to  Settings > Collaborators (on the left-hand menu under "Access") and adding the peoples.

## Markdown Quick Start Guide

### Core Syntax

- **Headings:** Use one to six `#` symbols at the start of a line (e.g., `# H1` for main heading, `## H2` for sub-heading).
- **Bold:** Wrap text in double asterisks or underscores: `**bold**`.
- **Italics:** Wrap text in single asterisks or underscores: `*italic*`.
- **Lists:** Use hyphens (`-`), plus signs (`+`), or asterisks (`*`) for unordered lists, and numbers for ordered lists.
- **Links:** Use `[Text](URL)`.
- **Images:** Use `![Alt Text](ImageURL)`.
- **Blockquotes:** Use `>` before the text.
- **Code:** Use backticks (`` `code` ``) for inline code or triple backticks (\`\`\`) for fenced code blocks.

### Key Concepts

- **Plain Text Formatting:** You can read and write Markdown in any text editor, making it portable and future-proof.
- **File Extension:** Saved with the `.md` extension.
- **Flavors:** Many platforms use "flavors" of Markdown that add features (e.g., GitHub Flavored Markdown supports tables and task lists).

### Why Use It?

- **Efficiency:** Faster than using a mouse to format text.
- **Portability:** Works on any operating system.
- **Readable:** Readable even as raw text.