# Bug Bounty Vulnerability Submission — LaTeX Template

A short, single-vulnerability write-up in the style of a HackerOne/Bugcrowd report — much smaller
than a full engagement report, but still split into a preamble and a finding file rather than one
monolithic file, matching the rest of this collection.

## Structure

```
main.tex                 -- header block + \input of the finding
preamble/preamble.tex    -- packages, colours, boxes, macros
finding/finding.tex      -- the single vulnerability write-up
```

## Quick start

1. Set `\reporttarget` (the program/target name), `\reportdate` in `preamble/preamble.tex`.
2. Fill in `finding/finding.tex`: summary, steps to reproduce, PoC payload, impact, suggested fix.
3. Search for `\fillme{` to find every placeholder.
4. Build with `pdflatex main.tex`, or open in Overleaf.

To submit more than one vulnerability, copy `finding/finding.tex` (e.g. `finding-2.tex`) and add
a second `\input` line to `main.tex` — most bounty platforms still want one report per
vulnerability, so check the program's policy first.

This template ships with no client data, no real vulnerability details — only placeholder/example
content, using the same design system as the rest of this collection.
