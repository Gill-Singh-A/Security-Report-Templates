# Security Assessment Report — LaTeX Template

A modular LaTeX template for a static / white-box security assessment report (e.g. a source-code
audit of an internal application or module), using the same dark-blue-and-red design system as the
other templates in this collection but organised around a **class-and-root-cause** narrative
rather than a chronological engagement narrative: findings are grouped by vulnerability class, and
a dedicated section calls out the small number of systemic root causes that generate most of them.

## Structure

Each report element lives in its own subdirectory, containing one `.tex` file of the same name:

```
main.tex                                       -- master file, \input's every element in order
preamble/preamble.tex                          -- packages, colour palette, boxes, macros
cover/cover.tex                                 -- title page
executive-summary/executive-summary.tex         -- summary, severity + class tables, roadmap
scope-methodology/scope-methodology.tex         -- subject/scope, approach, severity definitions
risk-posture/risk-posture.tex                   -- auth-requirement stats, sink prevalence, risk-by-class
systemic-root-causes/systemic-root-causes.tex   -- the R1, R2, ... architectural root causes
exploitation-playbooks/exploitation-playbooks.tex -- one PoC playbook per vulnerability class
findings-catalog/findings-catalog.tex           -- full finding-by-finding catalogue (F-001, ...)
appendix/appendix.tex                           -- secret-location index, exposed-file inventory
```

## Quick start

1. Set `\reportsystem` and `\reportdate` at the bottom of `preamble/preamble.tex`.
2. Fill in `cover/cover.tex`.
3. Write the executive summary, then the systemic root causes (R1, R2, ...) — these are what tie
   the whole report together.
4. For each vulnerability class, add one `\subsection` block to `findings-catalog/findings-catalog.tex`
   per finding (copy the F-001/F-002 example blocks) and one playbook to `exploitation-playbooks/exploitation-playbooks.tex`.
5. Every `\fillme{...}` marker (renders as a yellow inline box) is a prompt to replace with real
   content — search for `\fillme` to find them all.
6. Build with `pdflatex main.tex` run twice (for the ToC), or open in Overleaf.

## Requirements

A standard TeX Live / MiKTeX install with: `tcolorbox`, `mdframed`, `titlesec`, `fancyhdr`,
`tikz`, `tabularx`, `booktabs`, `enumitem`, `seqsplit`, `microtype`, `hyperref`.

## Design system macros

| Macro | Purpose |
|---|---|
| `\critical` `\high` `\medium` `\low` | Inline coloured severity badges |
| `\sgCrit` `\sgHigh` `\sgMed` `\sgLow` `\sgInfo` | Compact severity tags for the findings-catalog table cells |
| `\criticalbox` / `\highbox` / `\infobox{title}` / `\notebox` | Callout boxes |
| `\codebox[title]{...}` | Dark-themed code/PoC listing |
| `\fpath{...}` | Breakable monospace path (wraps long file paths anywhere) |
| `\fillme{...}` | Yellow "placeholder — fill this in" marker |

This template ships with no client data, no real findings, no credentials, and no source-code
excerpts from any real system — only placeholder/example content demonstrating the structure and
design system.
