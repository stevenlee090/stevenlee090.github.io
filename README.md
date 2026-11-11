# tangled reflections

Source for https://stevenlee090.github.io/, built with Jekyll and the [Minima](https://github.com/jekyll/minima) theme.

- Theme: Minima pinned to an upstream commit in `Gemfile`. To upgrade, bump the `ref`, run `bundle update minima`, and preview locally.
- Overrides: only `_includes/sub-footer.html` (MathJax). Anything else not in this repo comes from the theme.
- Deploy: `.github/workflows/pages.yml` builds on every push/PR and deploys `master` to GitHub Pages.

Local preview:

```sh
bundle install
bundle exec jekyll serve
```
