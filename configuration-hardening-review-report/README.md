# Configuration Hardening Review Report — LaTeX Template

A modular LaTeX template for a CIS-benchmark-style configuration hardening review: automated
scan + manual verification, pass/fail per control, rather than an exploit-driven finding catalogue.

## Structure

```
main.tex
preamble/preamble.tex                       -- packages, colours, boxes, macros (+ pass/fail badges)
cover/cover.tex
executive-summary/executive-summary.tex     -- pass-rate KPI, results-by-category table
scope-methodology/scope-methodology.tex     -- benchmark used, sampling, approach, result definitions
benchmark-results/benchmark-results.tex     -- full pass/fail table per benchmark category
findings-catalog/findings-catalog.tex       -- deep-dive on high-risk failing controls
recommendations/recommendations.tex
appendix/appendix.tex                       -- tools used, host inventory
```

## Quick start

1. Set `\reporttarget`, `\reportdate`, `\reportstatus` in `preamble/preamble.tex`.
2. Fill in `cover/cover.tex` naming the benchmark and version used.
3. Mirror the benchmark's own category structure in `benchmark-results/benchmark-results.tex`,
   marking each control `\pass` / `\fail` / `\notapplicable`.
4. Deep-dive any high-risk failures in `findings-catalog/findings-catalog.tex`.
5. Search for `\fillme{` to find every placeholder.
6. Build with `pdflatex main.tex` run twice, or open in Overleaf.

## Design system macros

Shared set, plus benchmark-check badges: `\pass`, `\fail`, `\notapplicable`.

This template ships with no client data — only placeholder/example content.
