# Prompting Sustainability — Project Site (Single Page)

A single-page static site for the *Prompting Sustainability* research project.
All content lives in `index.html`; the sticky top navigation smooth-scrolls
to each section.

## File structure

```
site/
├── index.html       The whole site — all sections in one file
├── style.css        Stylesheet
├── README.md        This file
└── images/          Figures used on the page
    ├── examples_cluster.png
    ├── examples_transformation.png
    ├── example_generated.jpg
    └── segmented_example.jpg
```

## How the navigation works

- Each top-bar link points to a section anchor: `#home`, `#about`, `#papers`,
  `#datasets`, `#funding`, `#news`, `#team`.
- `scroll-behavior: smooth` in CSS makes the jump animated.
- A small IntersectionObserver script at the bottom of `index.html` highlights
  the currently visible section's nav link with an underline.
- `scroll-padding-top: 72px` in CSS ensures sections don't sit hidden
  underneath the sticky nav when you click a link.

## Editing content

All sections are in `index.html`. Search for the `<!-- ============ NAME ====` 
banner comments to find each section quickly:

- **Hero copy** — search for `<section id="home">`
- **About / methodology / findings** — search for `<section id="about">`
- **Papers** — search for `<section id="papers">`. Each paper is one `<li>`
  inside `<ul class="papers-list">`. Change the `<span class="paper-status">`
  to `Published` or `Under Review` once a paper status changes.
- **Datasets** — search for `<section id="datasets">`
- **Funding** — search for `<section id="funding">`. Add a new grant by
  copying the existing `<li>` block.
- **News** — search for `<section id="news">`. A template comment shows
  how to add an entry. Once you have at least one entry, delete the
  `<div class="news-empty">` block.
- **Contact** — search for `<section id="contact">`. Replace name,
  affiliation, email, and links to update your details.

## Deploying to GitHub Pages

1. Push the contents of this folder to a GitHub repository.
2. In **Settings → Pages**, set the source branch and folder.
3. Save. The site publishes at
   `https://<your-username>.github.io/<repo-name>/`.

## Notes

- Font is **Arial** throughout (set in the `body` rule of `style.css`).
- No external CSS or JS dependencies — everything works offline.
- The IntersectionObserver script is the only JavaScript on the page,
  ~20 lines, no libraries.
