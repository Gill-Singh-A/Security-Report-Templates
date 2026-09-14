# Physical Security Assessment Report — LaTeX Template

A modular LaTeX template for an on-site physical penetration test: tailgating, badge cloning,
lock bypass, and post-access network testing.

## Structure

```
main.tex
preamble/preamble.tex
cover/cover.tex
executive-summary/executive-summary.tex   -- test results summary table
scope-methodology/scope-methodology.tex   -- in-scope sites, RoE, methodology
findings-catalog/findings-catalog.tex     -- one finding per successful bypass
recommendations/recommendations.tex
appendix/appendix.tex                     -- tools used, photo log reference
```

## Quick start

1. Set `\reporttarget`, `\reportdate`, `\reportstatus` in `preamble/preamble.tex`.
2. Fill in `cover/cover.tex` and `scope-methodology/scope-methodology.tex` (site, RoE, authorisation contact).
3. Add one finding block per successful bypass to `findings-catalog/findings-catalog.tex`.
4. Search for `\fillme{` to find every placeholder.
5. Build with `pdflatex main.tex` run twice, or open in Overleaf.

This template ships with no client data, no real facility details or photos — only
placeholder/example content.
