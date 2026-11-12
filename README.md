# base-css

Responsive base layer (tokens, reset, safe areas, centered container) for phone, tablet and desktop. One plain CSS file, no build step.

## Use

pnpm (Git dependency, versions are Git tags; pins the commit in the lockfile):

```
pnpm add -D github:Neyu703/base-css#v1.0.0
```

```ts
import "@neyu703/base-css/base.css";
```

```scss
@use "@neyu703/base-css/scss/mixins" as *;
```

Apps without a build step copy the file out of `node_modules` instead (see `coords-checklist`, script `sync:base-css`).

Static page or submodule:

```html
<link rel="stylesheet" href="vendor/base-css/base.css">
```

Vite/Sass app: `import "../vendor/base-css/base.css";` before the app styles.

Sass apps additionally get mixins (text styles, `card`, `grouped-list`, `filled-button`, ...) that build on the tokens: `@use "../../vendor/base-css/scss/mixins" as *;`. `base.css` stays the single source of truth for tokens and layout; Sass can load it directly (`@use "vendor/base-css/base"`), so there is no generated parallel copy to keep in sync.

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
