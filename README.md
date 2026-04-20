# Code With ABS

**Tagline:** Web development explained for self learners — in plain language.

**Live site Netlify:** [code-with-abs.netlify.app](https://code-with-abs.netlify.app/)

**Live site Github Pages:** [abdulrehmanabs.github.io/codewithabs](https://abdulrehmanabs.github.io/codewithabs/Index.html)

This repository is a **static, single-page** front-end: one HTML document, one stylesheet, and image assets. There is **no build step** and **no JavaScript framework** — only HTML and CSS (plus a small inline `<style>` block for hover effects on the sidebar buttons).

---

## What This Page Does

The page presents **Code With ABS** as a learning-focused brand: a hero with the site title, calls-to-action for HTML/CSS/JavaScript tutorials, a **search** field (UI only), a **Recent Articles** feed built as cards, repeated **social** and **newsletter** blocks, a **sidebar** with animated support/resource buttons and tag filters, and a **footer**. Most internal links use `href="#"` as placeholders for future routes or sections.

---

## Tech Stack

| Layer | Choice |
|--------|--------|
| Markup | HTML5 (`index.html`) |
| Styling | External `home.css` + a few rules in `<style>` inside `index.html` |
| Scripts | None (no `app.js`; forms and search are not wired to a backend) |
| Fonts | System stacks (e.g. Product Sans / Montserrat–style sans for body; Libre Baskerville / serif stack for the main heading) |

---

## Project Files

| File | Role |
|------|------|
| `index.html` | Full page structure: nav, hero, main column, sidebar, footer |
| `home.css` | Layout, typography, components, media queries, scrollbar styling |

**Referenced by `index.html` (ensure these exist for a complete local preview):**

- `home.css` — required
- `logo.svg` — navbar logo
- `images/Black_Gold_logo.png` — favicon (path uses lowercase `images/`)
- `Images/` — article thumbnails and card link targets (path uses capital `Images/`). Filenames include: `JS data storage.jpg`, `JS dialogs.png`, `JS timeouts.jpg`, `JS date and time.jpg`, `JS interpret URLs.png`, `JS intro to DOM.jpg`

If your images live at the repo root instead, either move them into an `Images/` folder to match the HTML or update the `src` / `href` paths in `index.html`.

---

## Page Structure (Top to Bottom)

### 1. Navigation (`nav`)

- **Logo** — links to `#` (home anchor)
- **Links:** HOME, TAGS, NEWSLETTER — all `#` placeholders
- **Behavior:** Sticky bar at the top with a coral/salmon background (`#f0967f`)

### 2. Hero (`home-header`)

- **Title:** “Code With ABS”
- **Subtitle:** “Web development explained for normal people!”
- **Buttons:** HTML TUTORIALS, CSS TUTORIALS, JAVASCRIPT TUTORIALS — placeholder links
- **Helper link:** “Don't know which to learn first?” — `#`

### 3. Main layout (`container`)

Two columns on wide screens; the layout **wraps** on smaller widths (see **Responsive design**).

**Left column (`large-container`):**

- **Search** — `<input type="search">` with placeholder “Search The Web…” (not connected to search logic)
- **Recent Articles** — heading with gradient text (class `linearGradientcolortotext`)
- **Article cards (`card`)** — each includes:
  - Thumbnail linking to the full image in a new tab (`target="_blank"`)
  - Title and excerpt
  - Footer with a **Javascript** tag link and a **date**
- Between some cards, **social** blocks (“Find Code The Web on:”) with Reddit and Twitter (generic `https://reddit.com` / `https://twitter.com/` — replace with your real profiles)
- **Newsletter (`Email`)** — email field + “Here We Go..” submit; `action="#"` (no server)

**Right column (`small-container`):**

- **Support / resource pills** — two pill-shaped buttons (“Resources!”, “Support me”) linking to Buy Me a Coffee (`https://www.buymeacoffee.com/`); hover expands a white circle (`.outerbox` / `.Width350`) via CSS in the page `<style>`
- **Spread the word** — Email, Facebook, Twitter, LinkedIn (`#` placeholders)
- **Topic tags** — Others, HTML, CSS, JAVASCRIPT, Back-End, Meta (`#`)

### 4. Footer (`body-footer`)

- “All Rights Reserved by © Code With ABS *2023*”

---

## Styling Highlights (`home.css`)

- **Colors:** Warm palette — coral header (`#f0967f`), dark brown text accents (`#5b1b0b`), light pink page background (`rgb(245, 232, 232)`), button browns and salmon highlights
- **Gradient text:** `.linearGradientcolortotext` uses a WebKit gradient clip for the “Recent Articles” title
- **Custom scrollbar:** WebKit scrollbar styled in coral/brown tones
- **Selection:** Blue-tinted `::selection` for highlighted text
- **Cards:** Rounded corners, shadows, hover-friendly links (`.card-link`)
- **Responsive breakpoints** (approximate): 1000px, 800px, 655px, 510px, 400px — adjusting margins, font sizes, flex behavior, hiding nav links on very small screens, stacking email inputs, constraining card image height, etc.

---

## How to Run Locally

No install or bundler required.

1. Clone or download this repository.
2. Open `index.html` in a browser **or** serve the folder with any static server (recommended so paths behave consistently):

   ```bash
   cd /path/to/codewithabs
   python3 -m http.server 8080
   ```

   Then visit `http://localhost:8080` and open `index.html` (e.g. `http://localhost:8080/index.html`).

---

## Deployment

The project is suitable for any **static host** (Netlify, GitHub Pages, Cloudflare Pages, etc.). The README’s live link points to **Netlify**; connect the repo and set the publish directory to the project root (or the folder containing `index.html`).

---

## Customization Checklist

- Replace `#` links with real URLs for tutorials, tags, newsletter, and share buttons
- Point Buy Me a Coffee and social links to your actual pages
- Wire the newsletter `<form>` to your provider (e.g. Buttondown, Mailchimp, Netlify Forms) or a small serverless function
- Add backend or client-side search if you want “Search The Web…” to do more than UI
- Align **asset paths** (`images/` vs `Images/`, `logo.svg`) with how you organize files
- Refresh footer year and copyright text as needed

---

## License / Credits

Content and design are for the **Code With ABS** project. Update this section if you adopt a specific open-source license or third-party asset licenses.
