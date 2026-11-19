# Vincent McDowell Jr. portfolio

Two pages, no build step, no dependencies beyond Google Fonts:

- `index.html`: the home page (experience, projects, education, about, résumé request)
- `story.html`: the scrollytelling "My story" page
- `site.css`: the design system both pages share (colors, type, header, buttons, cards, form fields)
- `images/`: put your photos here (currently just `portrait.jpg`, the home page portrait)

## 1. Put it on GitHub Pages (about 10 minutes)

1. Sign in to GitHub and create a new **public** repository. If you name it `YOUR_USERNAME.github.io`, the site will live at `https://YOUR_USERNAME.github.io/`. Any other name works too; the site then lives at `https://YOUR_USERNAME.github.io/REPO_NAME/`.
2. Upload `index.html`, `story.html`, `site.css`, `README.md`, and the `images` folder. (On the repo page: **Add file → Upload files**, then **Commit changes**.) GitHub won't keep an empty folder, so add a photo to `images` before uploading, or create the folder later when you add your first image.
3. Open **Settings → Pages**. Under **Build and deployment**, set **Source** to *Deploy from a branch*, choose the `main` branch and the `/ (root)` folder, and save.
4. Wait a minute or two, then open the URL shown at the top of the Pages settings. Both pages are live: the home page at `/` and the story at `/story.html`.

Every later change (a new photo, a filled-in metric) is just another upload and commit. The site updates within a minute.

## 2. Make the résumé form send you email (about 5 minutes)

The request form is built for [Formspree](https://formspree.io), which is free for up to 50 submissions a month and needs no server.

1. Create a free Formspree account with `vincentmcdowelljr@gmail.com` and click **New form**.
2. Formspree gives you an endpoint like `https://formspree.io/f/abcdwxyz`. Copy the id at the end.
3. In **both** `index.html` and `story.html`, find `YOUR_FORM_ID` (it appears once in each file) and replace it with that id.
4. Submit a test request from your live site. Formspree asks you to confirm your email address the first time; after that, every request lands in your inbox with the recruiter's name, email, company, role, job link, work arrangement, and message.

Until you do this, the form shows the "Something went wrong" message with your email address as a fallback, so nobody gets stuck.

## 3. Add photos whenever you have them

Only the home page portrait is live. Every other image spot is still in the HTML, in its original position, but switched off with the `hidden` attribute so visitors never see an empty frame. Search each file for `hidden>` to list them:

- `index.html`: three project photos (`<div class="img" hidden>`)
- `story.html`: the hero portrait (`<div class="portrait" hidden>`) and six story-card images (`<div class="media" hidden>`)

To switch one on:

1. Put the photo in the `images` folder (JPG or PNG, ideally under 500 KB; 1600 px wide is plenty).
2. Find the matching slot in the HTML. The bracketed text describes the photo that was planned for it.
3. Delete the word `hidden` and replace the bracketed text with an `<img>` line, for example:

   ```html
   <div class="img">
     <img src="images/uno32-shield.jpg" alt="Custom PCB shield mounted on the Uno32">
   </div>
   ```

   The frame crops and scales the photo automatically, and the layout goes back to image-plus-text on its own.

Always write a short `alt` description. It helps screen readers and search engines.

## 4. Other placeholders to fill in

The metrics, team sizes, and About me sentence are filled in. What is left:

- Photo slots (see section 3)
- Your GitHub link: there is a commented-out `<a>` tag in the footer of each page; replace `YOUR_USERNAME` and remove the comment markers

## 5. Changing colors, fonts, or shared components

Both pages load `site.css`. The palette and type scale are CSS variables at the top of that file, each with a comment saying what it is for, so a color changed there changes on both pages:

| Variable | Value | Used for |
|---|---|---|
| `--bg` | `#F7F9FC` | Page background |
| `--surface` | `#FFFFFF` | Cards and content surfaces |
| `--surface-2` | `#EEF2F7` | Alternate sections and subtle containers |
| `--text` | `#172033` | Headings and important content |
| `--text-2` | `#334155` | Body text |
| `--muted` | `#55657A` | Dates, captions, supplementary detail |
| `--navy` | `#1B2D5B` | Dark sections, hover states, emphasis |
| `--blue` | `#2E5090` | Buttons, links, interactive accents |
| `--gold` | `#F5C518` | Occasional highlights (never body text on a light surface) |
| `--border` | `#CBD5E1` | Cards and section dividers |

The header, buttons (`btn-primary`, `btn-secondary`), cards, chips, and form fields are also defined once in `site.css`. Layout that belongs to only one page stays in that page's own `<style>` block.

## 6. Optional: a custom domain

Buy a domain (around $12 a year from any registrar), then in the repo's **Settings → Pages** enter it under **Custom domain** and follow GitHub's DNS instructions. GitHub provides the HTTPS certificate automatically.
