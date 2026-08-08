# Ben Tye — portfolio site

A static site. No build step, no dependencies, no framework. Every file is plain HTML, CSS and a few lines of vanilla JavaScript, so it will run on any host that serves files.

## Files

| File | What it is |
| --- | --- |
| `index.html` | The whole site — markup, styles and script in one file |
| `404.html` | Not-found page, styled to match |
| `og-image.png` | Social preview card (1200×630) shown when the link is shared |
| `favicon.svg` | Browser tab icon |
| `robots.txt` | Allows search engines to index the site |
| `Ben-Tye-CV.pdf` | **You need to add this.** The download buttons link to this exact filename |

## Before publishing

Seven things still need filling in. They are highlighted in pink with a dashed underline so you cannot miss them on the page. To find them in the code, search `index.html` for `todo`.

1. Email address (appears twice — the `mailto:` link and the visible text)
2. LinkedIn URL
3. GitHub URL
4. Degree start year
5. Degree classification
6. B&Q employment dates
7. One concrete personal deliverable on Formula Student

Then:

- Add your CV to this folder, named exactly `Ben-Tye-CV.pdf`
- Delete the `.todo` CSS rule at the end of the stylesheet in `index.html` (the last rule, marked with a comment) to remove the pink highlighting
- Once you know your live address, replace `og:url` and the two `og-image.png` paths in the `<head>` with full URLs, e.g. `https://bentye.co.uk/og-image.png`. Social platforms need absolute URLs; relative ones will not resolve

## Publishing it

### GitHub Pages — free, custom domain supported

1. Create a GitHub account if you do not have one
2. Create a new **public** repository named `bentye.github.io` (substitute your username)
3. Upload every file in this folder to the root of that repository
4. Go to **Settings → Pages**, set Source to `Deploy from a branch`, branch `main`, folder `/ (root)`, and Save
5. Wait a minute or two. The site appears at `https://bentye.github.io`

### Netlify — free, drag and drop

1. Create a Netlify account
2. Go to **Sites** and drag this entire folder onto the drop zone
3. It deploys immediately to a random subdomain, which you can rename in **Site settings → Change site name**

Cloudflare Pages and Vercel work the same way, as does any traditional host with FTP access — upload the files and you are done.

### A custom domain

A `.co.uk` domain costs roughly £8–12 a year. Buy one from any registrar, then point it at your host: GitHub Pages and Netlify both have a "custom domain" setting that walks through the DNS records. `bentye.co.uk` on a CV reads considerably better than a `github.io` subdomain.

## Editing it later

Open `index.html` in any text editor. The structure is commented by section — hero, focus, work, capabilities, background, contact. Colours and fonts are CSS custom properties in the `:root` block at the top of the stylesheet, so changing the accent colour everywhere is a one-line edit.

To add a fourth project, copy any `<article class="proj">` block and edit the contents. The layout adapts automatically.

## Notes on how it is built

- **Fonts** load from Google Fonts. If you would rather not depend on that, download Archivo, Source Serif 4 and JetBrains Mono, put the files alongside the HTML and swap the `<link>` for `@font-face` rules
- **Accessibility**: keyboard focus is visible throughout, the animated figure has a text description, and everything animated stops for anyone who has "reduce motion" enabled in their operating system
- **No tracking or analytics.** Nothing to disclose in a cookie banner, and nothing to slow the page down
