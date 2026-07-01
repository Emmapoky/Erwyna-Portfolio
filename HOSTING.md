# Hosting Guide — erwyna.dev (or whatever domain you pick)

Everything below is free. You just need a GitHub account.

---

## Part 1 — Put your portfolio online (5 min)

**Easiest option: Netlify Drop**

1. Go to https://app.netlify.com/drop
2. Drag your entire `Erwyna Portfolio` folder onto the page
3. You'll get a live URL like `stellar-daisy-a3b2c1.netlify.app` instantly
4. In Site settings you can rename it to `erwyna.netlify.app` (or buy a custom domain later)

**Better option: GitHub Pages**

1. Create a new public repo on GitHub called `erwynasoo.github.io` (use your actual GitHub username)
2. From this folder, run in Terminal:
   ```
   git init
   git add .
   git commit -m "portfolio v1"
   git branch -M main
   git remote add origin https://github.com/erwynasoo/erwynasoo.github.io.git
   git push -u origin main
   ```
3. In the repo Settings → Pages → set Source to `main` branch
4. It'll be live at `https://erwynasoo.github.io` within a minute

Both options auto-serve `index.html` — nothing else to configure.

---

## Part 2 — Make your projects actually launch (this is what you asked about)

Each "▶ Launch Demo" button opens an iframe modal. Right now the URL is blank so it shows a "not deployed yet" message. Once you deploy each app, paste the URL into the button's `data-demo="..."` attribute in `index.html`.

### CommentSense (Streamlit → Streamlit Community Cloud)
1. Push the CommentSense repo to your own GitHub (fork or copy from `taabishfrl/CommentSense`)
2. Go to https://streamlit.io/cloud and sign in with GitHub
3. Click "New app" → pick the repo → point at the main Streamlit script
4. Click Deploy. You'll get a URL like `https://commentsense.streamlit.app`
5. In `index.html`, find the CommentSense button and change `data-demo=""` to `data-demo="https://commentsense.streamlit.app"`

### Knowva (Next.js → Vercel)
1. Go to https://vercel.com and sign in with GitHub
2. Import the `knowva` repo
3. Vercel auto-detects Next.js — just click Deploy
4. You'll get `https://knowva.vercel.app`
5. Paste that into the Knowva button's `data-demo=""` in `index.html`
6. **Note:** Firebase env vars need to be added in Vercel Project Settings → Environment Variables

### Toxic Atmosphere (Java desktop game — can't run in browser)
No live demo possible for a Java game without heavy porting. The YouTube walkthrough button is the right call here — keep it as is.

### Superstore Dashboard (Tableau)
If you have a Tableau Public account, publish the workbook there — you'll get an embeddable URL you can add as a "Launch Demo" button (I left this as walkthrough-only for now since it's Tableau). If you want, publish it and let me know the URL and I'll wire the button in.

---

## Part 3 — Fill in the empty screenshot slots

Drop these into `/Users/erwynasoo/Erwyna Portfolio/assets/images/` with these exact filenames — the "screenshot →" placeholders vanish automatically:

- `profile.jpg` — your photo (portrait, ~800×1000px works well)
- `commentsense.png` — Streamlit dashboard screenshot
- `knowva.png` — either of your Knowva screenshots
- `fit2099.png` — game console screenshot from the walkthrough
- `etw2001.png` — Superstore dashboard screenshot

---

## Part 4 — Custom domain (optional)

- Buy `erwyna.dev` or `erwynasoo.com` on Namecheap (~$12/year)
- In Netlify or Vercel, add the domain in the dashboard and follow the DNS instructions
- HTTPS is automatic

---

## Small tweaks to do before shipping

1. Add your LinkedIn URL in the contact section (currently `#`)
2. Confirm your GitHub username in the social link (I guessed `erwynasoo`)
3. Update the bio in the About section if the copy doesn't sound like you
