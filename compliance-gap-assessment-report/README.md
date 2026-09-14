# Compliance Gap Assessment Report — LaTeX Template

A modular LaTeX template for a control-by-control compliance readiness assessment (PCI-DSS,
ISO 27001, SOC 2, or similar) — a gap register rather than a vulnerability finding catalogue.

## Structure

```
main.tex
preamble/preamble.tex                     -- packages, colours, boxes, macros (+ compliance-status badges)
cover/cover.tex
executive-summary/executive-summary.tex   -- overview, compliance-by-domain table
scope-methodology/scope-methodology.tex   -- framework, approach, status definitions
control-domains/control-domains.tex       -- per-domain control tables (one subsection per domain)
gap-register/gap-register.tex             -- consolidated list of all gaps found
remediation-roadmap/remediation-roadmap.tex -- prioritised actions with target dates
appendix/appendix.tex                     -- evidence index, interviewees
```

## Quick start

1. Set `\reporttarget`, `\reportdate`, `\reportstatus` in `preamble/preamble.tex`.
2. Fill in `cover/cover.tex` and name the framework/version being assessed against.
3. Add one subsection per control domain to `control-domains/control-domains.tex`, one row per
   control, using `\compliant`/`\partiallycompliant`/`\noncompliant`/`\notapplicable`.
4. Roll every non-compliant/partial control into `gap-register/gap-register.tex` and
   `remediation-roadmap/remediation-roadmap.tex`.
5. Search for `\fillme{` to find every placeholder.
6. Build with `pdflatex main.tex` run twice, or open in Overleaf.

## Design system macros

Shared set, plus control-status badges: `\compliant`, `\partiallycompliant`, `\noncompliant`,
`\notapplicable`.

This template ships with no client data — only placeholder/example content.
