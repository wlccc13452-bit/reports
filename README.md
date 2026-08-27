# reports

Published EPAD ToBrowser HTML for [GitHub Pages](https://wlccc13452-bit.github.io/reports/) and Notion embed.

| | |
|--|--|
| GitHub | https://github.com/wlccc13452-bit/reports |
| Pages | https://wlccc13452-bit.github.io/reports/ |
| Parent checkout | `building-x/reports/` (nested git, **not** a submodule) |

`building-x` gitignores this tree so HTML / GLB / IFC never enter the parent repo.

## Current reports

- [LHKQ(20260510)[T1]](./LHKQ_20260510_T1_ReportAI.html)

## Git

```text
cd reports
git status
git add -A
git commit -m "Publish report"
git push origin main
```

GitHub Pages: Settings → Pages → Source **Deploy from a branch** → `main` / `/` (root). Add `.nojekyll` so files that start with `_` are served.

Do not use Git LFS: Pages does not serve LFS pointers.
