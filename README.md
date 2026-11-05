# Vincent McDowell Jr. portfolio

Two pages, no build step, no dependencies beyond Google Fonts:

- `index.html`: the home page (experience, projects, education, about, résumé request)
- `story.html`: the scrollytelling "My story" page
- `images/`: put your photos here (empty for now)

## 1. Put it on GitHub Pages (about 10 minutes)

1. Sign in to GitHub and create a new **public** repository. If you name it `YOUR_USERNAME.github.io`, the site will live at `https://YOUR_USERNAME.github.io/`. Any other name works too; the site then lives at `https://YOUR_USERNAME.github.io/REPO_NAME/`.
2. Upload `index.html`, `story.html`, `README.md`, and the `images` folder. (On the repo page: **Add file → Upload files**, then **Commit changes**.) GitHub won't keep an empty folder, so add a photo to `images` before uploading, or create the folder later when you add your first image.
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

Each image spot is a placeholder frame. To fill one:

1. Put the photo in the `images` folder (JPG or PNG, ideally under 500 KB; 1600 px wide is plenty).
2. Find the matching frame in the HTML. Each has a comment above it showing the exact line to add, for example:

   ```html
   <div class="img">
     <img src="images/uno32-shield.jpg" alt="Custom PCB shield mounted on the Uno32">
   </div>
   ```

   Replace the bracketed placeholder text with the `<img>` line. The frame crops and scales the photo automatically.

Always write a short `alt` description. It helps screen readers and search engines.

## 4. Other placeholders to fill in

Search each file for `[` to find them:

- `[X]` metrics in the experience and project sections
- `[X]-person team` and `[team size]` on the drone and robot soccer projects
- `[Add a sentence or two on what first got you into robotics.]` in About me
- Your GitHub link: there is a commented-out `<a>` tag in the footer of each page; replace `YOUR_USERNAME` and remove the comment markers

## 5. Optional: a custom domain

Buy a domain (around $12 a year from any registrar), then in the repo's **Settings → Pages** enter it under **Custom domain** and follow GitHub's DNS instructions. GitHub provides the HTTPS certificate automatically.
