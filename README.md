# Goldcrest Capital Solutions — JAMstack Site

Static HTML/CSS/JS site ready to deploy to **Cloudflare Pages** via GitHub.

---

## 📁 Project structure

```
goldcrest-capital/
├── index.html          ← Single-page site (all CSS & JS inline)
├── images/
│   ├── hero.jpg        ← Replace: hero section (right panel) — 1200×900px recommended
│   ├── about.jpg       ← Replace: About section — 900×700px recommended
│   └── process.jpg     ← Replace: Process section — 900×700px recommended
├── _headers            ← Cloudflare Pages security & cache headers
└── README.md
```

---

## 🚀 Deploy to Cloudflare Pages

1. Push this folder to a **GitHub repository**
2. Go to [Cloudflare Pages](https://pages.cloudflare.com/) → **Create a project**
3. Connect your GitHub account and select the repo
4. Set **Build settings**:
   - Framework preset: `None`
   - Build command: *(leave empty)*
   - Build output directory: `/` *(or the folder name if nested)*
5. Click **Save and Deploy** — done ✅

---

## 🖼️ Replacing placeholder images

Each `images/*.jpg` file is a labelled placeholder. Simply drop in your own photos with the **same filenames**:

| File | Where it shows | Recommended size |
|---|---|---|
| `images/hero.jpg` | Hero section right panel | 1200 × 900 px |
| `images/about.jpg` | About / Nosotros section | 900 × 700 px |
| `images/process.jpg` | Process / Proceso section | 900 × 700 px |

Supported formats: `.jpg`, `.webp`, `.png` — just update the `src` attribute in `index.html` if you change extensions.

---

## ✏️ Common customisations

| What | Where in index.html |
|---|---|
| Company name | Search `Goldcrest Capital` |
| Phone number | Search `(503) 2264-3458` |
| Email | Search `info@goldcrest-capital.com` |
| WhatsApp link | Search `wa.me/` |
| Instagram / social | Search `@goldcrest.capital` |
| Colours | `:root` CSS variables at top of `<style>` |
| Google Fonts | `<link>` tag in `<head>` |

### Colour tokens (`:root`)

```css
--sky:   #5BBBD6;   /* Primary — CTAs, accents, icons   */
--gold:  #E8C46A;   /* Secondary — process button, stars */
--dark:  #1C2B3A;   /* Text headings, footer background  */
```

---

## 📬 Wiring the contact form

The form currently shows a visual success state on click. To make it actually send data, add one of these:

### Option A — Netlify Forms (if migrating to Netlify)
Add `netlify` attribute to the `<form>` tag.

### Option B — Cloudflare Workers (recommended)
Create a Worker that receives a POST request and forwards it to an email via SendGrid / Mailgun.

### Option C — Formspree (easiest)
1. Sign up at [formspree.io](https://formspree.io)
2. Wrap the inputs in `<form method="POST" action="https://formspree.io/f/YOUR_ID">`
3. Remove the `onclick="handleSub(this)"` JS handler

---

## 🔒 Security headers

The `_headers` file configures Cloudflare Pages with strict security headers automatically on deploy.

---

*Built with plain HTML · CSS · Vanilla JS — no build step required.*
