# RACC GitHub Pages site

This repository publishes the RACC information page at:

<https://rensutheart.github.io/>

The current maintained RACC implementation is the napari plugin:

- GitHub: <https://github.com/rensutheart/napari-racc>
- PyPI: <https://pypi.org/project/napari-racc/>

The old standalone Python utility is retained under `download/` for reproducibility, but it is no longer actively maintained.

## Local preview

If Ruby/Bundler are available:

```bash
bundle install
bundle exec jekyll serve
```

Then open <http://localhost:4000>.

## Main files

- `index.md` is the public landing page.
- `RACC.md` keeps historical notes for the legacy standalone utility.
- `download/` contains legacy ZIP releases.
- `assets/images/` contains screenshots used by the landing page.
