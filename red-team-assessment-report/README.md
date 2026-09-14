# Red Team / Adversary Simulation Report — LaTeX Template

A modular LaTeX template for a goal-oriented, stealth-focused red team engagement, distinct from a
straight penetration test: it narrates a single operation chronologically, maps techniques to
MITRE ATT&CK, and grades detection/response rather than cataloguing every possible vulnerability.

## Structure

```
main.tex
preamble/preamble.tex                       -- packages, colours, boxes, macros (+ detection badges)
cover/cover.tex                              -- objective, outcome, rules of engagement summary
executive-summary/executive-summary.tex      -- outcome, detection summary
objectives-scope/objectives-scope.tex        -- objectives, scope, RoE, threat profile emulated
operation-timeline/operation-timeline.tex    -- TikZ timeline + detailed action log
attack-narrative/attack-narrative.tex        -- initial access -> persistence -> lateral movement -> objective
mitre-mapping/mitre-mapping.tex              -- ATT&CK technique table with detection status
detection-response/detection-response.tex    -- blue-team performance observations
findings-catalog/findings-catalog.tex        -- individually-trackable control gaps
recommendations/recommendations.tex
appendix/appendix.tex                        -- tools/infrastructure, IOCs for hunting
```

## Quick start

1. Set `\reporttarget`, `\reportdate`, `\reportstatus` in `preamble/preamble.tex`.
2. Fill in `cover/cover.tex` and `objectives-scope/objectives-scope.tex`.
3. Write the narrative in `attack-narrative/attack-narrative.tex`, then back it with the timeline
   and the ATT&CK mapping.
4. Use `\detected` / `\partiallydetected` / `\undetected` consistently across the executive
   summary, MITRE mapping, and detection-response sections.
5. Search for `\fillme{` to find every placeholder.
6. Build with `pdflatex main.tex` run twice, or open in Overleaf.

## Design system macros

Shared set, plus: `\detected`, `\undetected`, `\partiallydetected`, `\objectiveachieved`.

This template ships with no client data, no real infrastructure/IOCs, no live malware source —
only placeholder/example content.
