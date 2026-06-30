Tally — split expenses with friends
A tiny, single-file expense splitter. Make a group, add who's in, log who paid for what, and Tally shows each person's balance plus the fewest payments needed to settle up. No accounts, no backend — it's one index.html you can host for free on GitHub Pages.
Features
Create, rename, switch, and delete groups
Add and remove people per group
Log expenses and split them only between the people who were involved (uneven cents are distributed fairly, so totals always balance)
Balances dashboard with a who-owes / who's-owed view
Settle up — the minimum set of payments to square the group
Copy a clean summary for any one person, or for the whole group
Pick your currency ($, €, £, ₹, ¥)
Export / Import your data as a JSON file
Installable to your phone's home screen (works offline once loaded)
Deploy to GitHub Pages
The only requirement: a file named index.html must live at the root of the repository — GitHub Pages serves it as the homepage. In this project that's the landing page; the app itself is app.html, and the homepage's "Open Tally" button links to it.
Files
index.html — the landing page (what visitors see first)
app.html — the Tally app
README.md — this file
Option A — GitHub website (no tools needed)
Sign in at https://github.com and click + → New repository.
Give it a name (e.g. tally), keep it Public, and click Create repository. (Free GitHub Pages requires a public repo. Private Pages needs a paid plan.)
On the repo page: Add file → Upload files, drag in index.html (and this README.md), then Commit changes.
Go to Settings → Pages (left sidebar). Under Build and deployment:
Source: Deploy from a branch
Branch: main  •  Folder: / (root)
Click Save.
Wait about a minute, refresh the Pages screen, and open the "Your site is live at…" link.
Option B — Command line (git)
git init
git add index.html README.md
git commit -m "Add Tally expense splitter"
git branch -M main
git remote add origin https://github.com/<your-username>/<repo>.git
git push -u origin main
Then enable Pages exactly as in Option A, step 4.
Your URL
https://<your-username>.github.io/<repo>/
For example, user isaac with repo tally → https://isaac.github.io/tally/.
Updating the site
Edit index.html and re-upload it (or git push). GitHub rebuilds the site automatically, usually within a minute.
Custom domain (optional)
In Settings → Pages → Custom domain, enter your domain and follow the DNS instructions GitHub shows.
Where your data lives
Tally stores everything in your browser's localStorage on the device you're using. It survives refreshes and restarts, but it is not synced across devices and will be lost if you clear the browser's site data, use a private tab, or (on iOS Safari) leave the site unopened for about a week.
Two things keep your data safe:
Export a backup (top bar) — this downloads a JSON file. Import it on any device to restore. This is the only backup that survives a cleared cache.
Add to Home Screen (your browser's Share menu). On iOS especially, a home-screen app gets its own, more durable storage that the weekly cleanup doesn't touch — and it opens full-screen like a normal app.
Tech
Plain HTML, CSS, and JavaScript in a single file. Two web fonts load from Google Fonts; everything else is self-contained. No build step, no dependencies.
