# Comprehensive Code Audit Report — LaTeX Template

A modular LaTeX template for a large, book-style source-code security audit (dozens of findings
across many categories), using the standard `report` document class with numbered chapters and
parts, rather than the banner-header design system used by the other templates in this
collection. Includes severity-coloured finding boxes, a two-part structure (findings, then
remediation), and three appendices.

## Structure

```
main.tex                                        -- master file: title page, Part I, Part II, appendices
preamble.tex                                     -- packages, colours, listing styles, finding-box macros
chapters/ch01_executive_summary.tex              -- severity tally, top risks, report structure
chapters/ch02_scope_methodology.tex              -- scope, methodology, confidence levels, limitations
chapters/ch03_example_category_one.tex           -- example category (Injection) -- copy this pattern
chapters/ch04_example_category_two.tex           -- example category (Broken Access Control)
chapters/ch05_example_category_three.tex         -- example category (Cross-Site Scripting)
chapters/ch06_dependencies.tex                   -- vulnerable/EOL dependency inventory
chapters/ch07_remediation_roadmap.tex            -- P0/P1/P2 prioritised roadmap (Part II)
appendices/app_A_finding_matrix.tex               -- full finding index table
appendices/app_B_evidence_index.tex               -- file/class -> finding cross-reference
appendices/app_C_runtime_checklist.tex            -- checklist for dynamic (re-)verification
Makefile                                         -- `make` builds main.pdf
```

## Quick start

1. Set `\reportsystem` and `\reportdate` at the top of `preamble.tex`.
2. Fill in the title page fields in `main.tex`.
3. For each vulnerability category found, copy one of the `ch0N_example_category_*.tex` files,
   rename it, add its `\input` line to `main.tex`, and add its chapter label to the cross-refs in
   `ch01_executive_summary.tex` and `ch07_remediation_roadmap.tex`.
4. For each finding, copy one `\begin{findingcritical}{ID}{Title}...\end{findingcritical}` block
   (swap the environment for `findinghigh`/`findingmedium`/`findinglow`/`findinginfo` to match
   severity) and add a row to `appendices/app_A_finding_matrix.tex`.
5. Every `\fillme{...}` marker (yellow inline box in the PDF) is a prompt to fill in.
6. Build with `make`, or `pdflatex main.tex` run three times (for parts/ToC/cross-refs), or open
   in Overleaf.

## Requirements

A standard TeX Live / MiKTeX install with: `tcolorbox` (with `most`), `titlesec`, `fancyhdr`,
`listings`, `tabularx`, `longtable`, `booktabs`, `enumitem`, `rotating`, `pdflscape`, `hyperref`.

## Design system macros

| Macro/Environment | Purpose |
|---|---|
| `\Critical` `\High` `\Medium` `\Low` `\Info` | Inline coloured severity badges |
| `findingcritical` / `findinghigh` / `findingmedium` / `findinglow` / `findinginfo` `{ID}{Title}` | Boxed-title finding environments |
| `\findmeta{label}{value}` | Inline metadata pair inside a finding box (Severity, Confidence, ...) |
| `\findsection{label}` | Bold inline sub-heading inside a finding box (Location, Description, PoC, Impact, Remediation) |
| `\Confirmed` / `\Suspected` | Confidence-level markers |
| `warningbox` / `notebox` | Callout boxes |
| `\code{}` `\file{}` `\cls{}` `\ep{}` | Monospace helpers (code, file path, class name, endpoint) |
| `\fref{label}` | Bold cross-reference to a finding section |
| `\tabCrit`/`\tabHigh`/`\tabMed`/`\tabLow`/`\tabInfo` | Coloured severity cells for tables |
| `\fillme{...}` | Highlighted "placeholder — fill this in" marker |

This template ships with no client data, no real findings, no credentials, and no source-code
excerpts from any real system — only placeholder/example content demonstrating the structure and
design system.
