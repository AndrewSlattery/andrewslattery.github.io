# aslattery.co.uk

Source for my academic website, served via GitHub Pages (Jekyll) from this repo.
The custom domain is set in `CNAME`. GitHub rebuilds the site automatically on push.

## Structure

| Path | What it is |
|------|------------|
| `index.md` | **The content** — intro, papers, talks. Edit this to update the site. |
| `_layouts/default.html` | Page frame: the header (name, email, links) and where the content is slotted in. |
| `assets/css/style.css` | All styling. |
| `_config.yml` | Jekyll configuration. |
| `files/` | PDFs (CV, talk slides/posters, thesis, master's essay). |

## Adding a paper or talk

Edit `index.md`: copy an existing bullet under the right heading and change the
details. Conventions:

- co-authors in bold links — `**[Name](https://...)**`
- venue in italics — `*[Venue](https://...)*`
- resources in brackets — `[ [arXiv](https://...) ]`, `[ [slides](files/...pdf) ]`
- the `{: .class}` line under each heading sets its colour — leave it attached to the heading.

## Updating the CV

The CV source is `files/CV/CV_Andrew_Slattery.tex` with bibliography
`files/CV/CV_Andrew_Slattery.bib`. It uses biblatex, so recompile with biber:

    pdflatex CV_Andrew_Slattery
    biber    CV_Andrew_Slattery
    pdflatex CV_Andrew_Slattery
    pdflatex CV_Andrew_Slattery

(or `latexmk -pdf CV_Andrew_Slattery.tex`), then commit the regenerated PDF.

## Previewing the site locally (optional)

    gem install bundler jekyll
    jekyll serve     # then open http://localhost:4000

## Note

Everything committed here is **public**. Keep private material out of the repo;
`.gitignore` already excludes `career/`.
