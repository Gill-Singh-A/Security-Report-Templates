# Executive Security Posture Report — LaTeX Template

A short, non-technical, board/executive-facing report summarising security posture over a
reporting period (typically quarterly) — trend metrics and KPI tiles rather than individual
technical findings. Uses the same design system as the rest of this collection, but is
deliberately brief.

## Structure

```
main.tex
preamble/preamble.tex          -- packages, colours, boxes, macros
cover/cover.tex
key-metrics/key-metrics.tex     -- KPI tiles + period-over-period metrics table
risk-trend/risk-trend.tex       -- multi-period severity trend table
top-risks/top-risks.tex         -- top business risks with owners
recommendations/recommendations.tex -- investment asks with rationale/cost
```

## Quick start

1. Set `\reporttarget`, `\reportdate`, `\reportstatus`, and `\reportperiod` in
   `preamble/preamble.tex`.
2. Fill in the KPI tiles and trend table with real numbers pulled from your tracking system.
3. Keep every section in plain, non-technical language — this report is for decision-makers, not
   engineers.
4. Search for `\fillme{` to find every placeholder.
5. Build with `pdflatex main.tex` run twice, or open in Overleaf.

This template ships with no client data — only placeholder/example content.
