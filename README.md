# Martzen.nl

Persoonlijke blog over security, infrastructure, en development.

🌐 **Live:** [martzen.nl](https://martzen.nl)

## Theme

Deze site gebruikt het [Chirpy](https://github.com/cotes2020/jekyll-theme-chirpy/) theme v7.4.1 als volledig lokale fork (geen gem dependency).

**Credits:** Theme created by [Cotes Chung](https://github.com/cotes2020) - [MIT License](https://github.com/cotes2020/jekyll-theme-chirpy/blob/master/LICENSE)

## Development

```bash
bundle install && npm ci
npm run build
bundle exec jekyll serve
```

Site draait op [http://localhost:4000](http://localhost:4000)

## Deployment

Automatisch via GitHub Actions naar GitHub Pages.

## Theme Updates

Lokale fork van Chirpy v7.4.1. Upstream als remote `chirpy` toegevoegd voor updates.

### Update Workflow

```bash
# Check nieuwe versies
git fetch chirpy --tags
git log v7.4.1..v7.5.0 --oneline

# Test in branch
git checkout -b test-update
git merge chirpy/v7.5.0
npm run build && bundle exec jekyll serve

# Deploy als OK
git checkout main && git merge chirpy/v7.5.0
git push origin main
```

### Aangepaste Bestanden

Bij conflicts: behoud lokale versie of merge settings:

- `_includes/head.html` - CSS pad via `site.css_theme` variable
- `_config.yml` - Site config (lang, timezone, social)
- `.gitignore` - Lock files tracked

### Rollback

```bash
git revert <merge-commit>
# OF: git reset --hard HEAD~1 && git push --force
```
