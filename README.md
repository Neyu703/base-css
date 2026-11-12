# base-css

Responsive base layer (tokens, reset, safe areas, centered container) for phone, tablet and desktop. One plain CSS file, no build step.

## Use

Static page:

```html
<link rel="stylesheet" href="vendor/base-css/base.css">
```

Vite/Sass app: `import "../vendor/base-css/base.css";` before the app styles.

Add it as a submodule: `git submodule add https://github.com/Neyu703/base-css.git vendor/base-css`. For GitHub Pages workflows, use `actions/checkout` with `submodules: true`.

## Window-size classes

| Class | Width | Devices | `--gutter` | `--content-width` |
|---|---|---|---|---|
| compact | < 600px | iPhone 14 Plus, Galaxy A56 | 16px | 100% |
| medium | 600–839px | Galaxy Tab S10 FE / FE+ portrait | 24px | 640px |
| expanded | 840–1199px | tablets landscape | 32px | 760px |
| large | ≥ 1200px | desktop | 32px | 880px |

Mouse/trackpad (`hover: hover` + `pointer: fine`) lowers `--tap-target` from 44px to 36px.

## Tokens

Colors (light/dark via `prefers-color-scheme`), `--radius-*`, `--tap-target`, `--safe-*`, `--gutter`, `--content-width`, and the type scale `--text-*` (use as `font: var(--text-body)`).
