# Linding Yuan — personal website

Source for [https://yuanlinding.github.io/](https://yuanlinding.github.io/).

Built with [Hugo](https://gohugo.io/) + the
[HugoBlox Academic CV](https://github.com/HugoBlox/hugo-theme-academic-cv)
template. Content lives under `content/`; site config under `config/_default/`.

## Develop

```bash
# Hugo and Tailwind live in the conda env `web`
source /software/miniconda3/4.10.3/etc/profile.d/conda.sh
conda activate web
export PATH="$PWD/node_modules/.bin:$PATH"

# Live preview at http://localhost:1313
hugo server --disableFastRender

# Production build (writes to public/)
hugo --gc --minify
```

Pushes to `main` are auto-deployed to GitHub Pages via `.github/workflows/deploy.yml`.

## License

Content © Linding Yuan. Template under [MIT](./LICENSE.md).
