# Student HTML Projects Gallery

A hosted gallery for student HTML projects, deployed via GitHub Pages.

---

## Folder structure

```
student-projects/
├── index.html          ← gallery homepage (edit this to add students)
├── alice/
│   ├── index.html      ← Alice's project files
│   └── screenshot.png  ← optional thumbnail (16:9 works best)
├── bob/
│   ├── index.html
│   └── screenshot.png
└── ...
```

Each student gets their own folder. Their main file must be called `index.html`.
Any assets (images, CSS, JS) they reference should be inside their own folder too.

---

## Adding a student

1. Create a folder named after the student, e.g. `maya/`
2. Copy their project files into it (make sure the main file is `index.html`)
3. Optionally add a `screenshot.png` (1280x720 recommended)
4. Open `index.html` at the root and copy one of the existing card blocks
5. Update the card with the student's name, project title, description and folder path

### Card template

```html
<div class="card" data-name="student name here" data-filter="9B">
  <div class="card-thumb">
    <!-- With screenshot: -->
    <img src="maya/screenshot.png" alt="Maya's project">
    <!-- Without screenshot (remove the img line above and use this instead): -->
    <!-- <div class="thumb-placeholder" style="background:#fde8d8;">M</div> -->
    <div class="thumb-overlay">
      <a href="maya/index.html" target="_blank" class="open-btn">Open project ↗</a>
    </div>
  </div>
  <div class="card-body">
    <p class="card-tag">9B</p>
    <h2 class="card-title">Project Title Here</h2>
    <p class="card-desc">A short description of what the project does (2-3 sentences).</p>
  </div>
  <div class="card-footer">
    <span class="student-name">Maya Smith</span>
    <a href="maya/index.html" target="_blank" class="card-link">
      View
      <svg width="12" height="12" viewBox="0 0 12 12" fill="none" stroke="currentColor" stroke-width="1.5">
        <path d="M2 10L10 2M10 2H5M10 2V7"/>
      </svg>
    </a>
  </div>
</div>
```

**data-filter options:** `9B` | `9I` | `8B`

---

## Deploying to GitHub Pages (step by step)

### First time setup

1. Go to [github.com](https://github.com) and create a free account if you do not have one
2. Click **New repository** (the green button)
3. Name it `student-projects` (or anything you like)
4. Leave it **Public**, then click **Create repository**
5. Upload your files:
   - Click **Add file** → **Upload files**
   - Drag in your entire `student-projects/` folder contents
   - Scroll down and click **Commit changes**
6. Go to **Settings** → **Pages** (in the left sidebar)
7. Under **Branch**, select `main` and click **Save**
8. Wait about 60 seconds, then your site will be live at:
   `https://YOUR-USERNAME.github.io/student-projects/`

### Adding or updating projects later

1. Go to your repository on GitHub
2. Click **Add file** → **Upload files** (or navigate into a folder to replace individual files)
3. Upload the new or updated files
4. Commit the changes — the site updates automatically within a minute or two

### Using a custom domain (optional)

If you have your own domain (e.g. `cs-class.school`):
1. Go to **Settings** → **Pages**
2. Enter your domain under **Custom domain** and save
3. Add a `CNAME` record pointing to `YOUR-USERNAME.github.io` with your domain registrar

---

## Taking screenshots for thumbnails

The easiest way is to open the student's project in Chrome, then:

- Press `F12` to open DevTools
- Click the **Toggle device toolbar** icon (or press `Ctrl+Shift+M`)
- Set the size to `1280 x 720`
- Right-click on the page → **Capture screenshot**
- Save as `screenshot.png` inside the student's folder

---

## Customising the gallery

All styles are in `index.html` inside the `<style>` block at the top.
Key variables at the top of the style block:

```css
--accent: #c9440a;   /* change this to your school colour */
```

The header text ("Class of 2025", "Student HTML Projects") can be edited directly in the HTML.
The filter buttons (9B, 9I, 8B) can be renamed or extended by editing the `<button>` elements in the filter bar and updating the `data-filter` values on the cards to match.
