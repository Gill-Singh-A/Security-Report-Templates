# Social Engineering Assessment Report — LaTeX Template

A modular LaTeX template for a phishing/pretexting simulation campaign: click-rate metrics,
per-department breakdown, and awareness-training recommendations, rather than a technical
finding catalogue.

## Structure

```
main.tex
preamble/preamble.tex
cover/cover.tex
executive-summary/executive-summary.tex           -- headline metrics table
campaign-methodology/campaign-methodology.tex      -- pretexts used, ethics/RoE, delivery & tracking
campaign-results/campaign-results.tex              -- results by department, time-to-click
notable-observations/notable-observations.tex
recommendations/recommendations.tex
appendix/appendix.tex                              -- sample email(s), tools used
```

## Quick start

1. Set `\reporttarget`, `\reportdate`, `\reportstatus` in `preamble/preamble.tex`.
2. Fill in `cover/cover.tex` and `campaign-methodology/campaign-methodology.tex`.
3. Populate the per-department results table in `campaign-results/campaign-results.tex`.
4. Search for `\fillme{` to find every placeholder.
5. Build with `pdflatex main.tex` run twice, or open in Overleaf.

**Ethics note:** report results at department/aggregate level, not by named individual, unless
your organisation's HR/legal process specifically calls for it.

This template ships with no client data — only placeholder/example content.
