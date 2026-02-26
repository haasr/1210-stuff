# Getting Started with GitHub, Part 2: GitHub Pages

GitHub Pages is a free hosting service built into GitHub that serves static websites directly from a repository. Once configured, any HTML, CSS, and JavaScript you push to your repository will be accessible through a public URL — no server setup required. This is a great way to see a working draft of your website as you build it.

## 1. Understand Your GitHub Pages URL

Your site's URL is determined by your GitHub username and repository name:

```
https://<username>.github.io/<repository-name>/
```

For example, if your GitHub username is `jsmith` and your repository is named `csci-1210-phase1`, your site will be at:

```
https://jsmith.github.io/csci-1210-phase1/
```

If you ever forget your URL, you can find it in your repository's **Settings > Pages** section after completing the setup below.

## 2. Enable GitHub Pages

1. Open your repository in a web browser on github.com.
2. Click the **Settings** tab near the top of the repository page.
3. In the left-hand menu, click **Pages** (under the "Code and automation" section).
4. Under **Branch**, click the dropdown that says "None" and select your branch — typically `main`.
5. Leave the folder set to `/ (root)` unless your HTML files live in a subfolder (see note below).
6. Click **Save**.

GitHub will take a minute or two to build and deploy your site. Refresh the page and a green banner will appear with your live URL once it's ready.

> **Note on folder structure:** If your `index.html` is inside a subfolder (e.g., `phase1/`), you have two options: (a) change the Pages source folder to that subfolder if GitHub offers it, or (b) place a root-level `index.html` that redirects or links into the right phase folder. Keeping an `index.html` at the root of your repository is the simplest approach.

## 3. Verify Your index.html

GitHub Pages looks for a file named `index.html` at the root of whichever folder you configured as the source. If it finds one, that's what loads when someone visits your URL. If it doesn't find one, visitors will see a 404 error or a raw directory listing (depending on your settings).

Make sure:
- You have an `index.html` at the root of your source folder.
- The file is committed and pushed to the branch you selected in Step 2.

## 4. Push Changes and See Them Live

Every time you push a commit to your Pages-enabled branch, GitHub automatically rebuilds your site. The update usually takes 1–2 minutes to go live. The workflow looks like this:

1. Edit your HTML/CSS files locally.
2. In GitHub Desktop, review your changes, write a commit message, and click **Commit to main** (or your branch name).
3. Click **Push origin** to send your changes to GitHub.
4. Wait about a minute, then refresh your `github.io` URL to see the update.

You can check the build status by going to your repository on github.com and clicking the **Actions** tab — a green checkmark means your latest push deployed successfully; a red X means something went wrong (usually a configuration issue, not a problem with your HTML).

## 5. Troubleshooting Common Issues

**My site shows a 404.**
- Confirm that GitHub Pages is enabled in Settings > Pages and that a branch is selected.
- Make sure you have an `index.html` in the configured source folder and that it has been committed and pushed.
- Wait a couple of minutes and try again — the first deployment can take a little longer.

**My CSS or images aren't loading.**
- Check your file paths. Paths must be relative to the location of your HTML file. If your stylesheet is at `static/css/main.css` and your HTML is at the root, the link should be `href="static/css/main.css"`, not an absolute path starting with `/`.
- Capitalization matters on GitHub's servers (Linux). `Main.css` and `main.css` are treated as different files. Keep your filenames lowercase to avoid surprises.

**My changes aren't showing up.**
- Make sure you committed *and* pushed — a commit that hasn't been pushed only exists on your local machine.
- Hard-refresh your browser (`Ctrl+Shift+R` on Windows/Linux, `Cmd+Shift+R` on Mac) to bypass the browser cache.

**I see raw file listings instead of my page.**
- You're missing an `index.html` in the source folder. Add one and push it.

## 6. Sharing Your Site

Once your site is live, you can share the `github.io` URL with anyone — they don't need a GitHub account to view it. This is useful for getting feedback from peers, turning in working URLs for project milestones, or just showing off your work.

---

*See Part 1: Essentials for help setting up GitHub Desktop, creating repositories, and inviting collaborators.*
