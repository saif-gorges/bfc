# Baby Fight Club — Static Site

This is the new home for `babyfightclub.org`, rebuilt as a static HTML site for free hosting on GitHub Pages.

---

## What's in This Folder

| File | What it is |
|---|---|
| `index.html` | Home page |
| `2024-tour.html`, `2023-tour.html`, `2022-tour.html`, `2021-tour.html` | Past tour archive pages |
| `2023-scoreboard.html` | 2023 tournament scoreboard |
| `child-support.html` | Donation page |
| `style.css` | Shared stylesheet for all pages |
| `images/` | Put your saved images here (see `IMAGE_GUIDE.md`) |
| `CNAME` | Tells GitHub Pages your custom domain is `babyfightclub.org` |
| `.nojekyll` | Disables GitHub's Jekyll processing (we don't need it) |
| `IMAGE_GUIDE.md` | Which images to save from the old site, and what to name them |

---

## Order of Operations (Do These in This Order)

### Step 1 — Save your images from the old site (**before GoDaddy expires**)

Open `IMAGE_GUIDE.md` and follow it. This is the only thing with a hard deadline. Everything else can wait.

### Step 2 — Set up the GitHub repo

1. Make a free account at [github.com](https://github.com) if you don't have one.
2. Click **New repository**.
3. Name it anything — `babyfightclub`, `bfc-site`, whatever. (Using `babyfightclub.org` for a custom domain, the repo name doesn't actually matter.)
4. Make it **Public** (required for free GitHub Pages).
5. Check "Add a README" so the repo isn't empty.
6. Click **Create repository**.

### Step 3 — Upload the files

1. On your new repo page, click **Add file → Upload files**.
2. Drag *everything* from this folder into the upload box — all the `.html` files, `style.css`, the `images/` folder, `CNAME`, `.nojekyll`, and this `README.md`.
3. Scroll down, click **Commit changes**.

GitHub may hide the `.nojekyll` file because it starts with a dot. If you don't see it after upload, that's fine — it's there.

### Step 4 — Turn on GitHub Pages

1. In the repo, go to **Settings** (top nav).
2. In the left sidebar, click **Pages**.
3. Under "Source", pick branch **main** and folder **/ (root)**.
4. Click **Save**.
5. Wait 1–2 minutes. GitHub will give you a URL like `https://yourusername.github.io/reponame/`.
6. Open that URL — your site is live!

### Step 5 — Point `babyfightclub.org` at GitHub Pages

This is the DNS step. You'll do this at **whichever registrar you move the domain to** (Cloudflare or Porkbun — see "Moving the Domain" below).

At your registrar's DNS panel, add these records:

**`A` records** (four of them, all for the root `@`):
```
@   A   185.199.108.153
@   A   185.199.109.153
@   A   185.199.110.153
@   A   185.199.111.153
```

**`CNAME` record** (for `www`):
```
www   CNAME   yourusername.github.io
```

Replace `yourusername` with your actual GitHub username.

Then back in your repo's **Settings → Pages → Custom domain**, type `babyfightclub.org` and click Save. Check "Enforce HTTPS" once it's available (usually takes a few minutes to an hour).

---

## Moving the Domain Off GoDaddy

GoDaddy's domain renewal prices are inflated. Move the domain elsewhere:

### Option A — Cloudflare Registrar (recommended)
- Cheapest, at-cost pricing (~$10/yr for .org)
- Free DNS, free SSL, fast
- Go to [cloudflare.com](https://cloudflare.com), add your domain, follow their transfer steps.

### Option B — Porkbun
- Also cheap, has a friendlier UI than Cloudflare
- Go to [porkbun.com](https://porkbun.com), click Transfer.

### The Transfer Itself
1. Log into GoDaddy → My Domains → `babyfightclub.org` → **Unlock** the domain.
2. Get the **authorization code** (EPP code) from GoDaddy.
3. Start the transfer at your new registrar, paste the auth code.
4. Approve the transfer email GoDaddy sends you.
5. Wait ~5 days for the transfer to complete (normal).

**Important timing note**: Domains generally can't be transferred within 60 days of the last renewal. If GoDaddy just auto-renewed you, you'll need to either wait out that window or use their DNS (with your domain staying at GoDaddy) while GitHub Pages hosts the content. This is the cheapest escape if the 60-day window hits you — you only pay GoDaddy for the domain, $0 for hosting.

---

## Editing the Site Later

Since this is plain HTML, you can edit any page in any text editor (VS Code, TextEdit, Notepad++). 

- Change event dates/info: open the relevant `.html` file and edit the text.
- Add a new event: copy one of the `<article class="event">` blocks, paste it, change the details.
- Change colors or fonts: edit the variables at the top of `style.css`.

To push changes to the live site: GitHub website → navigate to the file → click the pencil icon → edit → **Commit changes**. Site updates in ~30 seconds.

If you want a nicer editing experience later, install VS Code and use GitHub Desktop for drag-and-drop uploads.

---

## Things I Couldn't Grab From the Old Site

A few things you'll need to fill in manually — I've flagged each in code comments:

1. **PayPal donation URL** — I don't know yours. Look in `child-support.html` for a PayPal comment.
2. **Instagram / Facebook / social links** — not currently in the nav. Add them to the footer if you want.
3. **Images** — see `IMAGE_GUIDE.md`.
4. **Contact form** — the old site had a reCAPTCHA-protected form. GitHub Pages is static-only, so you can't host a form that emails you. Easiest replacement: sign up for [Formspree](https://formspree.io) (free 50 submissions/month), or just put your email address as a `mailto:` link in the footer. I left the contact form out for now.
5. **Email subscribe** — same situation. Use [Mailchimp](https://mailchimp.com), [Buttondown](https://buttondown.email), or [Substack](https://substack.com) and embed their form, or skip it.

---

## Why GitHub Pages?

- **Free forever** with a custom domain and unlimited bandwidth for reasonable traffic.
- **Free HTTPS** (automatic SSL).
- **Fast** (served from a global CDN).
- **No vendor lock-in** — these are plain HTML files, you can move them anywhere in 5 minutes.

Trade-offs: no backend, no databases, no server-side anything. For a band/event-org site like BFC, that's totally fine — everything dynamic (betting forms, donations) lives at Google Forms / PayPal anyway.

---

## Questions?

Open the relevant HTML file in any browser (double-click it) to preview locally before uploading. Everything works offline except the Google Fonts, which load from the web.
