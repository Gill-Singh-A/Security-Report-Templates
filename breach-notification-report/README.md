# Data Breach Notification Report — LaTeX Template

A modular LaTeX template for the executive/legal-facing counterpart to a technical incident
forensic report: what happened, what data was affected, regulatory notification obligations, and
remediation actions — written for disclosure and governance, not for a technical audience.

## Structure

```
main.tex
preamble/preamble.tex
cover/cover.tex                                          -- privilege legend, key facts
incident-summary/incident-summary.tex                    -- what happened, key facts, who was notified
timeline/timeline.tex                                    -- TikZ timeline + detailed log
data-impact-assessment/data-impact-assessment.tex         -- data categories, individuals affected, evidence of misuse
regulatory-notifications/regulatory-notifications.tex     -- applicable frameworks, deadlines, status
remediation-actions/remediation-actions.tex               -- actions taken/planned with status
appendix/appendix.tex                                     -- external parties engaged, letter template reference
```

## Quick start

1. Set `\reporttarget`, `\reportdate`, `\reportstatus` in `preamble/preamble.tex`.
2. Fill in `cover/cover.tex`, including the privilege legend if prepared at counsel's direction.
3. Complete each section in plain language suitable for regulators, executives, and legal review.
4. Search for `\fillme{` to find every placeholder.
5. Build with `pdflatex main.tex` run twice, or open in Overleaf.

This template ships with no client data, no real incident details — only placeholder/example
content, using the same design system as the rest of this collection.
