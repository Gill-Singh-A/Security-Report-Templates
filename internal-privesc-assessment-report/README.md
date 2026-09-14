# Internal Network / Privilege-Escalation Assessment Report — LaTeX Template

A modular LaTeX template for an authenticated internal assessment across a fleet of hosts (a
"what can a low-privilege account do on every box" engagement), using the same design system as
the other templates in this collection, extended with **Confirmed vs. Mapped-not-tested** status
badges and a per-host candidate catalog for large fleets.

## Structure

```
main.tex                                     -- master file
preamble/preamble.tex                        -- packages, colour palette, boxes, macros
cover/cover.tex                               -- title page
executive-summary/executive-summary.tex       -- overview, severity table, confirmed-vs-mapped
scope-methodology/scope-methodology.tex       -- scope, approach, status definitions
host-inventory/host-inventory.tex             -- fleet table, foothold identity, risk tiers
risk-posture/risk-posture.tex                 -- candidate disposition stats, risk by category
systemic-root-causes/systemic-root-causes.tex -- the R1, R2, ... structural root causes
exploitation-playbooks/exploitation-playbooks.tex -- one PoC playbook per confirmed vector
findings/findings-catalog.tex                 -- headline findings index (table)
findings/F01-example-finding/finding.tex      -- one folder per headline finding, full detail
host-catalog/host-catalog.tex                 -- exhaustive per-host candidate dataset
loot-iocs/loot-iocs.tex                       -- credentials/keys/services worth reviewing
recommendations/recommendations.tex           -- prioritised recommendations
appendix/appendix.tex                         -- tools used, dataset pointer
```

## Quick start

1. Set `\reportfleet`, `\reportdate`, `\reportstatus` at the bottom of `preamble/preamble.tex`.
2. Fill in `cover/cover.tex` and `host-inventory/host-inventory.tex` with the real fleet facts.
3. For each headline finding, copy the `findings/F01-example-finding/` folder, update the
   `\label`/`\input` in `main.tex`, and add a row to `findings/findings-catalog.tex`.
4. Use `\confirmed` only for vectors actually exploited live; use `\mapped` for everything assessed
   applicable but not exploited.
5. Every `\fillme{...}` marker (yellow inline box in the PDF) is a prompt to fill in.
6. Build with `pdflatex main.tex` run twice, or open in Overleaf.

## Requirements

A standard TeX Live / MiKTeX install with: `tcolorbox`, `mdframed`, `titlesec`, `fancyhdr`,
`tikz` (incl. `shapes.geometric`, `arrows.meta`), `tabularx`, `booktabs`, `enumitem`, `seqsplit`,
`microtype`, `hyperref`.

## Design system macros

Adds to the shared set: `\info`, `\confirmed`, `\mapped` (status badges), `\confirmedbox`,
`\mitigationbox`. Also: `\critical`/`\high`/`\medium`/`\low`, `\criticalbox`, `\highbox`,
`\infobox{title}`, `\notebox`, `\codebox[title]{...}`, `\fpath{...}`, `\host{...}`, `\cve{...}`,
`\fillme{...}`.

This template ships with no client data, no real hostnames/IPs, no credentials, and no exploit
source code — only placeholder/example content demonstrating the structure and design system.
