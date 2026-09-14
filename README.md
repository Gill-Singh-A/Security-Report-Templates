# Security Report LaTeX Templates

A collection of 18 ready-to-use LaTeX templates for security-engagement reports. All 18 share one
dark-blue/red professional design system — colour palette, typography, boxed callouts, cover page
layout — but differ in structure and content to match the type of engagement they're for.

## Provenance

| Group | Templates | Origin |
|---|---|---|
| Core five | `web-app-pentest-report`, `security-assessment-report`, `incident-forensic-report`, `internal-privesc-assessment-report`, `comprehensive-code-audit-report` | **Distilled from a set of real security reports.** Every finding, hostname, credential, screenshot, and client identifier was stripped out and replaced with generic placeholder content and `\fillme{...}` prompts — but the design, theme, and file structure are exactly what the real reports used. |
| Extended thirteen | `mobile-app-pentest-report`, `cloud-security-assessment-report`, `red-team-assessment-report`, `wireless-security-assessment-report`, `executive-security-posture-report`, `breach-notification-report`, `compliance-gap-assessment-report`, `configuration-hardening-review-report`, `social-engineering-assessment-report`, `physical-security-assessment-report`, `dependency-supply-chain-risk-report`, `vulnerability-scan-summary-report`, `bug-bounty-submission-report` | **Not taken from any real report.** These cover engagement types the original report set didn't include. They were generated to match the same design system and the structural conventions of the core five (one file/subdirectory per report element, `\fillme{...}` placeholders, severity badges, etc.), based on how each type of report is typically structured in the security industry — not sourced from an actual client engagement. |

Every template ships with no client data, no real findings, no credentials, no screenshots — only
placeholder/example content.

## Templates

### Core five (derived from real reports)

| Template | Use it for | Structure |
|---|---|---|
| [`web-app-pentest-report/`](web-app-pentest-report/) | A black-box web application / API penetration test, narrated chronologically with one file per finding | `sections/` with a `findings/` subfolder |
| [`security-assessment-report/`](security-assessment-report/) | A white-box / static source-code security assessment of one system, organised by vulnerability class and systemic root cause | one subdirectory per report element (`cover/`, `executive-summary/`, `findings-catalog/`, ...) |
| [`incident-forensic-report/`](incident-forensic-report/) | Reporting a discovered active-compromise artifact (webshell, backdoor) — timeline, mechanism, IOCs | one subdirectory per report element |
| [`internal-privesc-assessment-report/`](internal-privesc-assessment-report/) | An authenticated internal assessment across a fleet of hosts, with per-host detail and Confirmed/Mapped status | one subdirectory per report element, plus `findings/F0N-.../` folders |
| [`comprehensive-code-audit-report/`](comprehensive-code-audit-report/) | A large, book-style audit with dozens of findings across many categories | `report` class with `chapters/` and `appendices/` |

### Extended thirteen (generated, same design system)

| Template | Use it for |
|---|---|
| [`mobile-app-pentest-report/`](mobile-app-pentest-report/) | An Android/iOS app penetration test (static + dynamic analysis, storage, transport security) |
| [`cloud-security-assessment-report/`](cloud-security-assessment-report/) | An AWS/Azure/GCP configuration review (IAM, network, data protection, logging) |
| [`red-team-assessment-report/`](red-team-assessment-report/) | A goal-oriented, stealth-focused adversary simulation with MITRE ATT&CK mapping |
| [`wireless-security-assessment-report/`](wireless-security-assessment-report/) | An on-site Wi-Fi penetration test (rogue AP, encryption, segmentation) |
| [`executive-security-posture-report/`](executive-security-posture-report/) | A short, non-technical, board/executive-facing periodic posture summary |
| [`breach-notification-report/`](breach-notification-report/) | The legal/regulatory-facing counterpart to an incident forensic report |
| [`compliance-gap-assessment-report/`](compliance-gap-assessment-report/) | A control-by-control readiness assessment (PCI-DSS, ISO 27001, SOC 2, ...) |
| [`configuration-hardening-review-report/`](configuration-hardening-review-report/) | A CIS-benchmark-style OS/server hardening review |
| [`social-engineering-assessment-report/`](social-engineering-assessment-report/) | A phishing/pretexting campaign results report |
| [`physical-security-assessment-report/`](physical-security-assessment-report/) | An on-site facility penetration test (tailgating, badge cloning, lock bypass) |
| [`dependency-supply-chain-risk-report/`](dependency-supply-chain-risk-report/) | An SBOM-based third-party/dependency risk assessment |
| [`vulnerability-scan-summary-report/`](vulnerability-scan-summary-report/) | A thin, tabular summary of a recurring automated vulnerability scan |
| [`bug-bounty-submission-report/`](bug-bounty-submission-report/) | A single-vulnerability write-up in the HackerOne/Bugcrowd style |

Each template is fully self-contained (its own `preamble`, sections, and `README.md`) and can be
copied out of this repository and used on its own.

## Shared design language

All 18 templates use one **design system**: a dark-blue/red professional palette (`PrimaryDark`,
`AccentRed`, ...), a full-bleed cover page, banner-style section headers, and a common set of
`tcolorbox` callouts (`criticalbox`, `highbox`, `infobox`, `notebox`) and severity badges
(`\critical`/`\high`/`\medium`/`\low`). Several add their own extra badges for their domain (e.g.
`\confirmed`/`\mapped` for privilege escalation, `\pass`/`\fail` for hardening reviews,
`\compliant`/`\noncompliant` for compliance gaps, `\aws`/`\azure`/`\gcp` for cloud, platform badges
for mobile). `comprehensive-code-audit-report` is the one exception: it uses a different,
`report`-class-based design better suited to very large finding counts organised into parts and
chapters.

## Picking a template

- Reporting on one external web/API target with a handful of findings? → `web-app-pentest-report`
- A static/white-box review of one system's source code? → `security-assessment-report`
- You found a live webshell/backdoor and need to report the incident? → `incident-forensic-report`
- Assessing many internal hosts from one foothold identity? → `internal-privesc-assessment-report`
- Dozens to 100+ findings across many categories, book-length? → `comprehensive-code-audit-report`
- An Android/iOS app? → `mobile-app-pentest-report`
- A cloud account/subscription configuration review? → `cloud-security-assessment-report`
- A stealth, objective-based adversary simulation? → `red-team-assessment-report`
- An on-site Wi-Fi assessment? → `wireless-security-assessment-report`
- A quarterly board/executive update? → `executive-security-posture-report`
- Notifying regulators/leadership after a breach? → `breach-notification-report`
- A PCI-DSS/ISO 27001/SOC 2 readiness check? → `compliance-gap-assessment-report`
- A CIS-benchmark hardening review? → `configuration-hardening-review-report`
- A phishing simulation campaign? → `social-engineering-assessment-report`
- An on-site facility/physical test? → `physical-security-assessment-report`
- A dependency/SBOM risk review? → `dependency-supply-chain-risk-report`
- A recurring automated scan report? → `vulnerability-scan-summary-report`
- One vulnerability for a bounty program? → `bug-bounty-submission-report`

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

Any standard TeX Live or MiKTeX installation. Across all 18 templates the packages used are:
`tcolorbox`, `mdframed`, `titlesec`, `fancyhdr`, `tikz`, `tabularx`, `booktabs`, `longtable`,
`enumitem`, `seqsplit`, `microtype`, `listings`, `rotating`, `pdflscape`, `hyperref`. All are part
of a standard `texlive-full` / `MiKTeX` install. Every template was compile-tested end-to-end with
`pdflatex` before being added to this repository.

## What is (and isn't) in this repository

No real hostnames, IP addresses, credentials, source-code excerpts, screenshots, or finding
content survive anywhere in this repository — only reusable design, structure, and illustrative
placeholder text. See **Provenance** above for which templates came from real reports (sanitized)
versus which were generated from scratch to match the same conventions. Treat all of them the same
way you'd treat any other public LaTeX report template.
