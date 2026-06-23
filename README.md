# aslattery.co.uk

Source for my academic website, served via GitHub Pages (Jekyll) from this repo.
The custom domain is set in `CNAME`. GitHub rebuilds the site automatically on push.

## Structure

| Path | What it is |
|------|------------|
| `_data/publications.yml` | **The content** — intro, papers, talks. Edit this to update the site. |
| `index.html` | Template that renders the data above into the page. |
| `_layouts/default.html` | Page frame: the header (name, email, links). |
| `assets/css/style.css` | All styling. |
| `_config.yml` | Jekyll configuration. |
| `files/` | PDFs (CV, talk slides/posters, thesis, master's essay). |

## Adding a paper or talk

Open `_data/publications.yml` and copy an existing entry under the right
section. Fields (all optional except `title`):

```yaml
- title: My new paper
  coauthors:
    - { name: Ada Lovelace, url: "https://example.com" }
  venue: Some Journal
  venue_url: "https://example.com"
  year: 2026
  note: submitted          # shown after an em dash, in italics
  links:
    - { label: arXiv, url: "https://arxiv.org/abs/..." }
```

You never need to touch HTML or CSS to add publications.

## Updating the CV

The CV source is `files/CV/CV_Andrew_Slattery.tex` with bibliography
`files/CV/CV_Andrew_Slattery.bib`. It uses biblatex, so recompile with biber:

    latexmk -pdf files/CV/CV_Andrew_Slattery.tex

then commit the regenerated `CV_Andrew_Slattery.pdf`.

## Previewing the site locally (optional)

GitHub builds the site automatically on push, so this is optional:

    gem install bundler jekyll
    jekyll serve     # then open http://localhost:4000

## Note

Everything committed here is **public**. Keep private material out of the repo;
`.gitignore` already excludes `career/`.
