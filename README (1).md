# FERNO portfolio

One self-contained file. No build step, no dependencies, no external requests except Google Fonts.
Open `index.html` in a browser, or drop the folder on Netlify / push it to GitHub Pages.

## Where the images go

All content lives in the `PORTFOLIO` object inside `index.html` (search for `PORTFOLIO CONFIG`).
Put your files in an `assets` folder next to `index.html`, then write the path. A full `https://` URL works too.

| What | Line (approx) | What to write |
|---|---|---|
| Profile photo | 1169 | `photo: "assets/ferno.jpg"` |
| Resume PDF | 1172 | `resume: "/resume/ferno-resume.pdf"` |
| Resume date | 1173 | `resumeUpdated: "August 2026"` |
| Project screenshots | 1305, 1335, 1365, 1396 | `{ label:"Revenue overview", img:"assets/dvd-1.png" }` |
| Certificates | 1423 | see the template comment right above it |
| Site URL + share image | 13, 19, 20, 25 | your domain and a 1200x630 preview image |

Folder layout:

```
index.html
assets/
  ferno.jpg
  dvd-1.png  dvd-2.png ...
  cert-python.jpg
resume/
  ferno-resume.pdf
```

Until a path resolves, the page shows a labelled placeholder instead of a broken image. Nothing is invented.

## Certificates

`certificates: []` is empty, so the whole section, its nav entry, and its metric are hidden on the live site.
Add one entry using the template comment and everything appears automatically. A category filter shows up on its own once there are four or more certificates in more than one category.

Fields you can leave as `""`: `credId`, `verify`, `img`. Empty ones are simply not rendered, so nothing looks fabricated.

## Project links

Every `links: { github:"", demo:"" }` is empty. Fill in a real URL and the button becomes live; leave it empty and it renders as "link pending" rather than pointing somewhere fake.

## Contact form

Validation and the success state work. Nothing is sent yet. In the submit handler there is a marked line where a `fetch()` to Formspree, Resend, or your own endpoint goes. The email button and copy button work today.

## Notes

- Technology logos are the official marks from Simple Icons, inlined as SVG paths. Excel, Dagster, Matplotlib and SQL have no licensable mark available, so they use neutral line glyphs in the right brand color rather than a fake logo.
- Colors and type are CSS custom properties in `:root`. Change `--blue` and the accent system follows.
- Violet is reserved for machine learning content only.
- Reduced motion, keyboard focus, semantic headings, and alt text are handled.


## Portfolio v2 update
- Recruiter-first data/AI positioning
- Six real GitHub projects connected
- Updated project case studies and roles
- Updated resume path and August 2026 resume label
- Contact form now opens a pre-filled email
- Added visible GitHub repository status on project cards
