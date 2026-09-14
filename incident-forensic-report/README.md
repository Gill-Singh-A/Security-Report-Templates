# Active Compromise / Incident Forensic Report — LaTeX Template

A modular LaTeX template for reporting a discovered active-compromise artifact (webshell, backdoor,
staged malicious files) — the incident-response counterpart to this collection's static assessment
templates. Same dark-blue-and-red design system, but organised around **what was found, when, and
what it means** rather than a finding-catalogue.

## Structure

```
main.tex                                            -- master file
preamble/preamble.tex                               -- packages, colour palette, boxes, macros
cover/cover.tex                                      -- title page
executive-summary/executive-summary.tex              -- overview, scope note, artifacts-at-a-glance
scope-methodology/scope-methodology.tex              -- subject/scope, investigation approach
attack-mechanism/attack-mechanism.tex                -- how the artifact technically works
webshell-inventory/webshell-inventory.tex            -- one subsection per artifact + consolidated list
timeline/timeline.tex                                -- TikZ timeline + detailed table + interpretation
database-compromise/database-compromise.tex          -- downstream data/credential exposure
indicators-of-compromise/indicators-of-compromise.tex -- on-disk / network / host IOCs for hunting
impact/impact.tex                                    -- business-level impact summary
recommendations/recommendations.tex                  -- containment / short-term / long-term actions
appendix/appendix.tex                                -- full artifact paths, rotation checklist
```

## Quick start

1. Set `\reportsystem` and `\reportdate` at the bottom of `preamble/preamble.tex`.
2. Fill in `cover/cover.tex` and the executive summary.
3. For each artifact found, copy the IC-01 block in `webshell-inventory/webshell-inventory.tex`
   and add a row to the consolidated list and to the timeline.
4. **Never** paste real secret values, live IPs, or verbatim malicious source into this report —
   describe locations and behaviour, and write "values withheld per rules of engagement" as shown
   in `database-compromise/database-compromise.tex`.
5. Every `\fillme{...}` marker (yellow inline box in the PDF) is a prompt to fill in.
6. Build with `pdflatex main.tex` run twice, or open in Overleaf.

## Requirements

A standard TeX Live / MiKTeX install with: `tcolorbox`, `mdframed`, `titlesec`, `fancyhdr`,
`tikz`, `tabularx`, `booktabs`, `enumitem`, `seqsplit`, `microtype`, `hyperref`.

## Design system macros

Same as `security-assessment-report/`: `\critical`/`\high`/`\medium`/`\low`, `\criticalbox`,
`\highbox`, `\infobox{title}`, `\notebox`, `\codebox[title]{...}`, `\fpath{...}`, `\fillme{...}`.

This template ships with no client data, no real artifacts/malware source, no credentials, and no
IP addresses — only placeholder/example content demonstrating the structure and design system.
