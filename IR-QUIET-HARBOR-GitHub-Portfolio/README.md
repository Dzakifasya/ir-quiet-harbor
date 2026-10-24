# Incident Response Case Study: QUIET HARBOR

![Status](https://img.shields.io/badge/status-completed-success)
![Type](https://img.shields.io/badge/project-academic%20simulation-blue)
![Focus](https://img.shields.io/badge/focus-DFIR%20%7C%20Incident%20Response-informational)

> **Academic simulation only.** This repository documents a fictional insider-threat and data-exfiltration exercise completed in a controlled training environment. It is not a real-world investigation, and it does not allege misconduct by any real person or organization.

## Overview

This case study covers first response and digital-forensics analysis for a simulated suspected data-exfiltration incident involving a research workstation, file-share access, outbound proxy activity, removable media, process execution evidence, and memory artifacts.

The exercise emphasized evidence preservation, lawful and proportionate scope, timeline reconstruction, cross-source correlation, and transparent handling of an integrity discrepancy.

## Exercise outcome

| Evaluation area | Result |
|---|---:|
| First-response decisions | 40 / 40 |
| Evidence analysis | 45 / 45 |
| Evidence integrity | 15 / 15 |
| **Overall result** | **100 / 100 — Grade A** |

The score is the result recorded by the exercise's automated evaluator. It reflects performance in this academic simulation, not a professional certification or independent validation of real-world incident-response experience.

## Scenario at a glance

- **Scenario:** Suspected insider-driven data exfiltration
- **Environment:** Simulated enterprise research workstation and supporting logs
- **Evidence sources:** Web-proxy logs, file-share access audit, device-installation logs, process/command-line listing, memory strings, and removable-media listing
- **Primary analytical tasks:** Correlate account activity, identify the external destination and transfer volume, reconstruct removable-media timing, and review evidence integrity
- **Key caveat:** One process-list artifact did not match its acquisition-manifest hash and recorded size. That discrepancy was documented, and conclusions relying on that artifact were treated cautiously and correlated with other sources.

## Response approach

1. **Coordinate and define authority.** Confirm written authorization, scope, and appropriate HR/Legal coordination before examining company assets.
2. **Preserve volatile evidence.** Prioritize memory and other volatile artifacts before lower-volatility sources when operationally appropriate.
3. **Document clock drift.** Record host time and reference time separately; preserve the original system clock and account for the offset during timeline reconstruction.
4. **Protect removable media.** Photograph and document the media in place, package it appropriately, and inspect it through a write blocker.
5. **Correlate evidence.** Compare proxy, file-share, device, process, and memory evidence rather than relying on a single artifact.
6. **Verify integrity.** Compare cryptographic hashes and recorded sizes against the acquisition manifest; document mismatches and avoid overstating conclusions.

## Repository contents

- [`docs/incident-summary.md`](docs/incident-summary.md) — sanitized incident summary and findings
- [`docs/response-methodology.md`](docs/response-methodology.md) — first-response decisions and rationale
- [`docs/evidence-integrity.md`](docs/evidence-integrity.md) — integrity discrepancy and cautious interpretation
- [`docs/chain-of-custody.md`](docs/chain-of-custody.md) — sanitized chain-of-custody principles and example
- [`docs/lessons-learned.md`](docs/lessons-learned.md) — lessons and improvement opportunities

## Skills demonstrated

- Digital forensics and incident response (DFIR) fundamentals
- Evidence acquisition and preservation planning
- Order-of-volatility reasoning
- Timeline reconstruction and clock-drift correction
- Log correlation across multiple evidence sources
- SHA-256 integrity verification
- Chain-of-custody documentation
- Careful reporting of limitations and uncertainty

## Limitations and ethics

This is a training case study based on a simulated evidence package. Identifiers, personal information, internal network details, exact file names, credentials, and raw evidence values have intentionally been omitted or generalized for public sharing. No raw evidence, passwords, internal IP addresses, or personal identifiers are included.

The analysis is limited to what the exercise evidence and evaluator supported. A process command line alone does not establish that a transfer completed; conclusions should be corroborated with independent logs and other artifacts.

## References

- RFC 3227 — *Guidelines for Evidence Collection and Archiving*
- NIST SP 800-86 — *Guide to Integrating Forensic Techniques into Incident Response*
- NIST SP 800-61 Rev. 3 — *Incident Response Recommendations and Considerations*
- ISO/IEC 27037 — *Guidelines for identification, collection, acquisition and preservation of digital evidence*

These references are listed as relevant professional guidance; this repository is an academic exercise and does not claim formal compliance or certification.

## Author's note

This project was completed as an academic incident-response simulation and received a recorded score of **100/100 (Grade A)**. The purpose of this repository is to demonstrate structured reasoning, evidence-handling discipline, and clear technical reporting while protecting sensitive details.
