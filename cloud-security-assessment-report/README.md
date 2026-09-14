# Cloud Security Configuration Assessment Report — LaTeX Template

A modular LaTeX template for a cloud provider configuration review (AWS/Azure/GCP), organised by
security domain (IAM, network, data protection, logging/monitoring) and benchmarked against a
CIS-style baseline, using the same design system as the rest of this collection.

## Structure

```
main.tex                                  -- master file
preamble/preamble.tex                     -- packages, colours, boxes, macros (+ provider badges)
cover/cover.tex
executive-summary/executive-summary.tex   -- overview, severity + domain tables
scope-methodology/scope-methodology.tex   -- accounts in scope, benchmark used, approach
iam-review/iam-review.tex                 -- IAM metrics + findings
network-security/network-security.tex     -- network exposure metrics + findings
data-protection/data-protection.tex       -- storage/encryption metrics + findings
logging-monitoring/logging-monitoring.tex -- audit logging posture + findings
findings-catalog/findings-catalog.tex     -- full finding index
recommendations/recommendations.tex
appendix/appendix.tex
```

## Quick start

1. Set `\reporttarget`, `\reportdate`, `\reportstatus` in `preamble/preamble.tex`.
2. Fill in `cover/cover.tex` and `scope-methodology/scope-methodology.tex` (provider, accounts,
   benchmark used).
3. Add one `\subsection{F-NN --- ...}` finding block per domain file as you find issues, and add a
   row to `findings-catalog/findings-catalog.tex`.
4. Search for `\fillme{` to find every placeholder.
5. Build with `pdflatex main.tex` run twice, or open in Overleaf.

## Design system macros

Shared set (`\critical`/`\high`/`\medium`/`\low`, `\criticalbox`, `\highbox`, `\infobox{title}`,
`\notebox`, `\codebox[title]{...}`, `\fillme{...}`), plus provider badges: `\aws`, `\azure`, `\gcp`.

This template ships with no client data, no real account IDs, resource names, or credentials —
only placeholder/example content.
