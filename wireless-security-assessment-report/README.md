# Wireless Network Security Assessment Report — LaTeX Template

A modular LaTeX template for an on-site wireless (Wi-Fi) penetration test: RF survey, encryption
assessment, rogue-AP/credential-capture testing, and segmentation checks.

## Structure

```
main.tex
preamble/preamble.tex
cover/cover.tex
executive-summary/executive-summary.tex
scope-methodology/scope-methodology.tex
wireless-environment/wireless-environment.tex   -- network survey table
findings-catalog/findings-catalog.tex
recommendations/recommendations.tex
appendix/appendix.tex                           -- tools used, AP inventory
```

## Quick start

1. Set `\reporttarget`, `\reportdate`, `\reportstatus` in `preamble/preamble.tex`.
2. Fill in `cover/cover.tex` and the network survey in `wireless-environment/wireless-environment.tex`.
3. Add one finding block per issue to `findings-catalog/findings-catalog.tex`.
4. Search for `\fillme{` to find every placeholder.
5. Build with `pdflatex main.tex` run twice, or open in Overleaf.

This template ships with no client data, no real SSIDs/BSSIDs/credentials — only
placeholder/example content, using the same design system as the rest of this collection.
