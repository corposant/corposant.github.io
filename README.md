# Pineau Group

A single-page site for Annika Pineau, Realtor. Static HTML — no build step, no framework, no dependencies. Just open `index.html` in a browser, or push the folder to GitHub Pages.

## Repo layout

```
.
├── index.html        ← the entire site
├── images/
│   ├── annika-portrait.jpg
│   └── pineau-logo.jpg
├── .nojekyll         ← tells GitHub Pages not to run Jekyll
└── README.md
```

## Deploy to GitHub Pages

1. Create a new GitHub repository (public if you want a free github.io URL, private requires a paid plan).
2. Push the contents of this folder to the `main` branch.
3. In the repo on github.com: **Settings → Pages**.
4. Under **Source**, choose `Deploy from a branch`, pick `main` and `/ (root)`, then **Save**.
5. Wait ~30 seconds. Your site appears at `https://<your-username>.github.io/<repo-name>/`.

### Custom domain (e.g. `pineaugroup.com`)

1. In **Settings → Pages → Custom domain**, enter the domain and save.
2. With your DNS provider, add either:
   - An `A` record on the apex (`@`) pointing to GitHub's IPs: `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`, **or**
   - A `CNAME` record on `www` pointing to `<your-username>.github.io`.
3. Back in **Settings → Pages**, enable **Enforce HTTPS** once GitHub has issued the cert (takes a few minutes).

## Editing the site

The whole page is in `index.html`. It's organized top-to-bottom in the same order it renders. A few common edits:

| Change | Where to look |
|---|---|
| Colors and fonts | The `:root` block at the top of `<style>`. Two key colors: `--wedge` (Wedgwood blue) and `--cream` (page background). |
| Hero copy | The `<section class="hero">` block. |
| About text | The `<section id="about">` block. |
| Testimonials | Four `<div class="letter">` blocks — duplicate one to add another. |
| Contact details | The `.contact-details` block — phone, email, Instagram. |
| Contact form | Set `action="https://formspree.io/f/YOUR_FORMSPREE_ID"` to your real Formspree endpoint. Or delete the form and embed something else. |

### Photos

Replace the files in `images/`. Filenames are referenced in three spots:

- `images/pineau-logo.jpg` — used once in the nav.
- `images/annika-portrait.jpg` — used twice (hero + about).

Keep the same filenames and the page picks them up automatically. Aim for ~1200×1500 portraits at 200–400 KB compressed.

## Contact form setup (Formspree)

1. Sign up at [formspree.io](https://formspree.io) (free tier handles up to 50 submissions/month).
2. Create a new form, give it any name.
3. Copy the form endpoint URL (looks like `https://formspree.io/f/xrgaqkpe`).
4. Open `index.html`, search for `YOUR_FORMSPREE_ID`, and replace the full action URL.
5. First submission triggers a confirmation email from Formspree — confirm and you're live.

Alternative: replace the `<form>` element with a Mailchimp/ConvertKit/Squarespace embed, or simply delete it and rely on the phone/email links.

## Tech notes

- Single self-contained HTML file (no external CSS or JS apart from Google Fonts).
- Fonts: Cormorant Garamond, Inter, and Caveat — loaded from Google Fonts with `display=swap`.
- Inline SVG favicon (small Wedgwood-blue "P" on cream) — no extra file needed.
- Hero portrait is preloaded for fastest LCP; the about portrait uses `loading="lazy"`.
- Open Graph and Twitter Card meta tags configured for social sharing previews.
- Respects `prefers-reduced-motion` — the candle stops flickering for users who've set that preference.
- Fully responsive at mobile, tablet, and desktop widths.

## License

Site content (copy, images of Annika, Pineau Group branding) © Pineau Group, all rights reserved.
Template code (HTML/CSS) — feel free to adapt for personal projects.
# corposant.github.io
