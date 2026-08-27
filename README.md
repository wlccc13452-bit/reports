# reports

Published EPAD ToBrowser HTML for [GitHub Pages](https://wlccc13452-bit.github.io/reports/) and Notion embed.

| | |
|--|--|
| GitHub | https://github.com/wlccc13452-bit/reports |
| Pages site | https://wlccc13452-bit.github.io/reports/ |
| Report (LHKQ) | https://wlccc13452-bit.github.io/reports/LHKQ_20260510_T1_ReportAI/ |
| Parent checkout | `building-x/reports/` (nested git, **not** a submodule) |

`building-x` gitignores this tree so HTML / GLB / IFC never enter the parent repo.

## Layout (BX-437)

```text
reports/
  .nojekyll
  index.html              ← listing
  LHKQ_20260510_T1_ReportAI/
    index.html            ← ToBrowser HTML
    assets/               ← vendor + media for this report only
```

Publish from Report Orchestrator (**Publish** header) runs bake → copy → git push → Pages → Notion.

## Git (manual)

```text
cd reports
git status
git add -A
git commit -m "Publish report"
git push origin main
```

GitHub Pages: Settings → Pages → **Deploy from a branch** → `main` / `/` (root).

Do not use Git LFS — Pages does not serve LFS pointers. Files ≥ 100 MB are skipped during Publish.

## Migrate legacy flat HTML

If an older publish used `reports/Foo.html` + shared `reports/assets/`:

```text
cd epad
uv run python -c "from pathlib import Path; import sys; sys.path.insert(0,'src'); from report_agent.publish_copy import migrate_flat_reports; print(migrate_flat_reports(Path('..')/'reports'))"
```

Then commit and push from `reports/`.
