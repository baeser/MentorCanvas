# DCS New Teacher Mentor Program

A web-based mentor program for Dexter Community Schools, aligned with Michigan's Standards for Mentoring and Induction of New Teachers, School Counselors, and Administrators (April 2026) and compliant with MCL 380.1526.

This is a single-page HTML site with three years of monthly mentoring guidance — Year 1 (Foundation), Year 2 (Refinement), and Year 3 (Independence). It's designed to be hosted on GitHub Pages and embedded into Canvas LMS as an iframe module.

## What's in this repo

- **`index.html`** — the entire program. Self-contained: all CSS and JavaScript embedded, no external dependencies. About 340KB.
- **`README.md`** — this file.
- **`LICENSE`** — Creative Commons Attribution 4.0 (lets other Michigan districts adapt this for their own programs with credit).
- **`.gitignore`** — ignores OS clutter and editor backups.

## Setting up the GitHub repo

If you don't already have a GitHub account, create one at github.com first.

### Option 1: Web UI (easiest, no command line)

1. Go to **github.com/new**
2. Repository name: `dcs-mentor-program` (or whatever you prefer)
3. Description: "DCS New Teacher Mentor Program"
4. Set to **Public** (required for free GitHub Pages on personal accounts)
5. Check **Add a README file** — you'll replace it in step 7
6. Click **Create repository**
7. On the repo page, click **Add file → Upload files**, then drag in `index.html`, `README.md`, and `LICENSE`. Commit the changes.

### Option 2: Command line (if you have git installed)

```bash
cd /path/to/repo-folder
git init
git add .
git commit -m "Initial commit: DCS Mentor Program"
git branch -M main
git remote add origin https://github.com/YOUR-USERNAME/dcs-mentor-program.git
git push -u origin main
```

## Enabling GitHub Pages

1. In your repo, click **Settings** (top right of repo page)
2. In the left sidebar, click **Pages**
3. Under "Build and deployment":
   - **Source:** Deploy from a branch
   - **Branch:** `main` (or `master` if that's your default)
   - **Folder:** `/ (root)`
4. Click **Save**
5. Wait 1–2 minutes. Refresh the Pages settings — you'll see a green message: "Your site is live at https://YOUR-USERNAME.github.io/dcs-mentor-program/"
6. Click that URL to confirm it loads

That URL is your public site. Bookmark it.

## Embedding in Canvas

Canvas supports embedded iframes through the Rich Content Editor. Here's the cleanest path:

### As a Canvas page

1. In your Canvas course, go to **Pages → New Page**
2. Title it "Mentor Program" (or similar)
3. In the Rich Content Editor, click the **HTML editor** toggle (looks like `</>` in the toolbar)
4. Paste the following, replacing the URL with your GitHub Pages URL:

```html
<iframe
  src="https://YOUR-USERNAME.github.io/dcs-mentor-program/"
  width="100%"
  height="900"
  style="border: none;"
  title="DCS New Teacher Mentor Program">
</iframe>
```

5. Click **Save & Publish**

The full program will render inside the Canvas page with working tabs, year selector, and all formatting intact.

### Notes on iframe sizing

- `height="900"` works well for desktop. For mobile-heavy classes you may want `height="1200"` or higher since the program scrolls within the iframe.
- If you want the iframe to size dynamically, that requires postMessage communication between the parent and iframe — complicated to set up in Canvas. Static height is simpler and works fine.

### Alternative: Direct Canvas page (no iframe)

If you'd rather have the content as a native Canvas page (not iframed), you can paste the contents of `<body>` directly into Canvas's HTML editor. **Tradeoff:** Canvas strips `<script>` tags, so the year selector and month tabs won't work — all 31 sections will render stacked. For a Canvas-native version, you'd need to break this into multiple Canvas pages (one per year, or one per month) and link between them. The iframe approach is much less work.

## Updating the program

Whenever you want to update the content (new monthly guidance, new resources, etc.), you have two options:

**Web UI:** Go to your repo, click `index.html`, click the pencil icon to edit, paste your updated HTML, scroll down and commit. GitHub Pages will rebuild automatically within ~1 minute.

**Command line:**
```bash
# replace index.html with your new file, then:
git add index.html
git commit -m "Update monthly content for [whatever]"
git push
```

The Canvas embed will pick up the new version automatically — no changes needed on the Canvas side.

## Updating without breaking links

The URL stays the same as long as you don't:
- Rename the repo
- Change your GitHub username
- Change the GitHub Pages source branch

## Adapting for other districts

This program is licensed under Creative Commons Attribution 4.0. Other Michigan districts are welcome to fork this repo, replace "DCS"/"Dexter" with their own district name, adjust the contact log link, and use it as their own program — with attribution to Dexter Community Schools.

## Questions / Issues

For DCS-internal questions: contact Ryan Baese.

For technical questions about the HTML/repo: open an issue in this repo or reach out to whoever maintains the program.

---

*Aligned with Michigan Department of Education Standards for Mentoring and Induction of New Teachers, School Counselors, and Administrators (April 2026) and compliant with MCL 380.1526.*
