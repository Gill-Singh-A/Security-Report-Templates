# Dependency & Supply-Chain Risk Report — LaTeX Template

A modular LaTeX template for an SBOM-based third-party/dependency risk assessment: known CVEs,
end-of-life components, license risk, and reachability analysis, deeper than a single
"Vulnerable Dependencies" chapter in a broader code audit.

## Structure

```
main.tex
preamble/preamble.tex
cover/cover.tex
executive-summary/executive-summary.tex   -- overview, severity table
scope-methodology/scope-methodology.tex   -- ecosystems, SBOM format, approach, severity defs
sbom-inventory/sbom-inventory.tex         -- inventory stats + notable components table
findings-catalog/findings-catalog.tex     -- one finding per notable dependency risk
recommendations/recommendations.tex
appendix/appendix.tex                     -- tools used, full SBOM pointer
```

## Quick start

1. Set `\reporttarget`, `\reportdate`, `\reportstatus` in `preamble/preamble.tex`.
2. Fill in `cover/cover.tex` and `scope-methodology/scope-methodology.tex`.
3. Populate `sbom-inventory/sbom-inventory.tex` with real counts, and add one finding per
   significant risk to `findings-catalog/findings-catalog.tex`.
4. Search for `\fillme{` to find every placeholder.
5. Build with `pdflatex main.tex` run twice, or open in Overleaf.

This template ships with no client data, no real dependency names/versions — only
placeholder/example content.
