# jaeheesong.com

Personal research site. Jekyll + GitHub Pages, no build step required —
GitHub compiles it on every push.

## Publish it

1. Create a public repo named exactly `jaeheesong.github.io`.
2. Upload everything in this folder to the root of that repo.
3. Settings → Pages → Source: "Deploy from a branch" → `main` / `(root)`.
4. Wait ~1 minute, then visit `https://jaeheesong.github.io`.

The `CNAME` file already contains `jaeheesong.com`, so once you point DNS at
GitHub the custom domain takes over. Do that only after the site looks right.

## Edit it

| What | Where |
|---|---|
| Name, roles, email, CV link, Scholar link | `_config.yml` |
| Bio, section order, teaching | `index.html` |
| Papers | one file per paper in `_papers/` |
| Photo | replace `assets/img/headshot.jpg` |
| PDFs (papers, slides, CV) | drop into `assets/papers/` |
| Colors and type | `assets/css/style.css` (variables at the top) |

### Adding a paper

Create any `.md` file in `_papers/`. The text below the front matter is the
abstract, which sits behind a toggle.

```markdown
---
category: working        # working · publication · wip · resource
order: 1                 # lower numbers appear first
title: "Paper Title"
url: /assets/papers/mypaper.pdf
byline: "with [Coauthor](https://url). March 2026. R&R, *Econometrica.*"
links:
  - name: Slides
    url: /assets/papers/myslides.pdf
media:
  - name: The Economist
    url: https://economist.com/...
---

Abstract text here.
```

`links` and `media` are optional. A section disappears automatically when it
has no entries, so delete the example files you do not need.

## Preview locally (optional)

Not required — you can edit files directly on GitHub and see the result in a
minute. If you want a local preview:

```bash
bundle install
bundle exec jekyll serve
```

Then open http://localhost:4000.
