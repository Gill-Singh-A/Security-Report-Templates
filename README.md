# Security Report LaTeX Templates

A collection of five ready-to-use LaTeX templates for security-engagement reports, distilled from
a set of real reports and stripped of all client-specific content. Each template keeps the
original design, theme, and file structure — colour palette, typography, boxed callouts, cover
page layout — but every finding, hostname, credential, screenshot, and client identifier has been
replaced with generic placeholder content and `\fillme{...}` prompts.

## Templates

| Template | Use it for | Structure |
|---|---|---|
| [`web-app-pentest-report/`](web-app-pentest-report/) | A black-box web application / API penetration test, narrated chronologically with one file per finding | `sections/` with a `findings/` subfolder |
| [`security-assessment-report/`](security-assessment-report/) | A white-box / static source-code security assessment of one system, organised by vulnerability class and systemic root cause | one subdirectory per report element (`cover/`, `executive-summary/`, `findings-catalog/`, ...) |
| [`incident-forensic-report/`](incident-forensic-report/) | Reporting a discovered active-compromise artifact (webshell, backdoor) — timeline, mechanism, IOCs | one subdirectory per report element |
| [`internal-privesc-assessment-report/`](internal-privesc-assessment-report/) | An authenticated internal assessment across a fleet of hosts, with per-host detail and Confirmed/Mapped status | one subdirectory per report element, plus `findings/F0N-.../` folders |
| [`comprehensive-code-audit-report/`](comprehensive-code-audit-report/) | A large, book-style audit with dozens of findings across many categories | `report` class with `chapters/` and `appendices/` |

Each template is fully self-contained (its own `preamble`, sections, and `README.md`) and can be
copied out of this repository and used on its own.

## Shared design language

The first four templates share one **design system**: a dark-blue/red professional palette
(`PrimaryDark`, `AccentRed`, ...), a full-bleed cover page, banner-style section headers, and a
common set of `tcolorbox` callouts (`criticalbox`, `highbox`, `infobox`, `notebox`) and severity
badges (`\critical`/`\high`/`\medium`/`\low`). Between them, they cover the four report
*shapes* found most often in practice: single narrative with per-finding files, per-section-file
modular, incident/forensic, and multi-host/fleet. The fifth template (`comprehensive-code-audit-report/`)
uses a different, `report`-class-based design better suited to very large finding counts organised
into parts and chapters.

## Picking a template

- Reporting on one external target with a handful of findings? → `web-app-pentest-report`
- A static/white-box review of one system's source code? → `security-assessment-report`
- You found a live webshell/backdoor and need to report the incident? → `incident-forensic-report`
- Assessing many internal hosts from one foothold identity? → `internal-privesc-assessment-report`
- Dozens to 100+ findings across many categories, book-length? → `comprehensive-code-audit-report`

## Using a template

1. Copy the template's folder to a new location (or use it directly as your report's repo).
2. Open its `README.md` for structure-specific instructions.
3. Set the report-wide placeholders (target/system name, date, status) at the top of its
   `preamble/preamble.tex` (or `preamble.tex`).
4. Search the project for `\fillme{` — every occurrence is a prompt for content you need to
   supply. They render as a highlighted inline box in the compiled PDF so unfinished sections are
   easy to spot.
5. Build with the template's `build.sh`/`Makefile`, plain `pdflatex` (run twice, or three times
   for the chapters template), or open the folder in Overleaf.

## Requirements

Any standard TeX Live or MiKTeX installation. Across the five templates the packages used are:
`tcolorbox`, `mdframed`, `titlesec`, `fancyhdr`, `tikz`, `tabularx`, `booktabs`, `longtable`,
`enumitem`, `seqsplit`, `microtype`, `listings`, `rotating`, `pdflscape`, `hyperref`. All are part
of a standard `texlive-full` / `MiKTeX` install.

## What is (and isn't) in this repository

These templates were derived from real security assessment reports, with every piece of
client-identifying or sensitive content removed during the process: no real hostnames, IP
addresses, credentials, source-code excerpts, screenshots, or finding content survive here — only
the reusable design, structure, and illustrative placeholder text. Treat them the same as any
other public LaTeX report template.
