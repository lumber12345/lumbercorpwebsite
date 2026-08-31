# Lumbercorp — Deploy to Render

This is a **static site** (no backend, no build step). It deploys on Render as a **Static Site**.

## Deploy steps

1. **Push to GitHub.** Create a repo and push this folder's contents. The repo root must contain `render.yaml` and the `lumbercorp/` folder:

   ```
   repo/
   ├── render.yaml
   ├── DEPLOY.md
   └── lumbercorp/
       ├── index.html        ← Matrix landing page
       ├── redpill.html      ← Red pill page (donate, Torn Rank Wars, Companion)
       └── matrix-city.jpg
   ```

2. **Create the site on Render.**
   - Go to **New → Blueprint**, select your repo. Render reads `render.yaml` and creates the `lumbercorp` static site automatically.
   - **Or** **New → Static Site**, connect the repo, set:
     - Build Command: *(leave blank)*
     - Publish Directory: `lumbercorp`

3. **Deploy** — Render publishes the folder. You'll get a URL like `https://lumbercorp.onrender.com`.

## Live URL out of the box
- `https://<your-site>.onrender.com/` → index.html
- `https://<your-site>.onrender.com/redpill.html` → red pill page

## Notes
- `render.yaml` (optional) just automates step 2; the manual **Static Site** option works too.
- The **Torn Rank Wars** button links out to `https://rankwars.onrender.com/` and **Companion** to `https://lumbercorp-companion.onrender.com/` — both are external, so nothing extra is needed here.
- The **donate** link goes to Torn (`torn.com/profiles.php?XID=4428819`).
- If you ever add a custom domain, update it in `render.yaml` under `domains:` and redeploy.
