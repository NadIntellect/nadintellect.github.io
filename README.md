# NadIntellect Lab — website

Static one-page site. No build step, no server code, no dependencies except Google Fonts.

## Contents

```
NadIntellect_Lab_site/
  index.html                              the whole site (HTML + CSS + JS inline)
  assets/
    NadIntellect_Lab_mobile_clean.avif    hero artwork, primary
    NadIntellect_Lab_mobile_clean.webp    hero artwork, fallback
    NadIntellect_Lab_mobile_clean.png     hero artwork, lossless master (last-resort fallback)
    NadIntellect_long_background.avif     long cosmic backdrop, primary
    NadIntellect_long_background.webp     long cosmic backdrop, fallback
  README.md
  CHANGELOG.md
```

## Publishing

Upload the contents of `NadIntellect_Lab_site/` to any static host, keeping the `assets/`
folder next to `index.html`. Nothing else is required.

- **Netlify Drop** — drag the folder onto https://app.netlify.com/drop
- **GitHub Pages** — commit the folder to a repository, then Settings → Pages → deploy from branch
- **Cloudflare Pages / Vercel** — "upload a folder" / static project, no framework preset

To preview locally, open `index.html` in a browser, or run `python3 -m http.server` in this folder.

## Placeholders to replace

Search `index.html` for these comments:

| Comment | What to put there |
| --- | --- |
| `REPLACE WITH LINKEDIN URL` | LinkedIn profile (two places: side rail, Contact list) |
| `REPLACE WITH X URL` | X profile (two places: side rail, Contact list) |
| `REPLACE WITH MANIFUND URL` | funding page (Support button and Contact list) |
| `CANONICAL / OG:URL` | real domain — add `<link rel="canonical">` and `og:url` once it exists |
| `FAVICON PLACEHOLDER` | the approved NadInLab logo, when the file is ready |
| `LOGO PLACEHOLDER` | the approved logo in the header, next to the wordmark |
| `TEMPORARY DESKTOP FALLBACK` | the approved horizontal desktop master, when it exists |

The email link `Evgeniygaluschak1@gmail.com` is live and needs nothing.

## Notes for whoever edits this next

- Mobile and desktop are one file. Desktop layout starts at 1024px; the fixed cosmic
  backdrop and the mobile typography scale apply below 1080px / 1024px.
- The hero artwork is never cropped: it is scaled to fit and the HTML copy is positioned
  in percentages of the art box.
- The cosmic backdrop is a fixed viewport layer. Scrolling does not move it. It drifts
  slowly on its own and crossfades to another region of the master once scrolling stops.
- `prefers-reduced-motion: reduce` disables the drift, the crossfade and all other motion.
- No analytics, no cookies, no third-party scripts. The only external request is Google Fonts.
