# Incident Summary — QUIET HARBOR

## Classification

**Academic simulation · Suspected insider-driven data exfiltration**

This document is a sanitized summary of a fictional training scenario. All identifying values and sensitive indicators have been generalized.

## Executive summary

A simulated security operations alert reported unusually large outbound traffic from a research workstation to an external file-sharing service. The exercise evidence set included proxy records, file-share access auditing, device-installation events, a process listing, strings recovered from a memory image, and a removable-media listing.

Correlation across these sources supported a scenario in which a user account accessed a restricted research folder, an encrypted archive was prepared, removable media was connected, and a transfer utility was invoked to send an archive to an external destination.

The exercise also contained an evidence-integrity issue: the process-list artifact's received SHA-256 digest and file size differed from the acquisition manifest. This limitation was explicitly documented. The process artifact was interpreted cautiously and considered alongside other evidence rather than treated as independently conclusive.

## Evidence categories

| Evidence ID | Generalized source | Analytical purpose |
|---|---|---|
| EV-001 | Web-proxy log | Identify outbound destination and estimate transfer volume |
| EV-002 | File-share access audit | Establish access to restricted files and relevant account activity |
| EV-003 | Device-installation log | Identify removable-media connection and reconstruct timing |
| EV-004 | Process and command-line listing | Examine suspicious process execution; integrity discrepancy noted |
| EV-005 | Strings extracted from memory image | Correlate in-memory artifacts with archive and transfer activity |
| EV-006 | Removable-media file listing | Review files present on the external medium |

## Findings supported by the exercise

- Multiple evidence sources were relevant to the suspected data-exfiltration sequence.
- Proxy and file-share logs were used together to connect access activity with outbound network behavior.
- A host-clock offset had to be accounted for when reconstructing the removable-media timeline.
- A process artifact had an integrity mismatch and therefore required cautious interpretation.
- The automated evaluator recorded a score of **100/100 (Grade A)** for the exercise submission.

## Important limitations

- This is not a real-world incident report.
- Raw usernames, hostnames, internal IP addresses, exact external indicators, exact file names, serial numbers, hashes, and credentials are intentionally excluded.
- The exercise score indicates correctness against the simulation's evaluator; it is not a certification of professional competence.
- Findings should not be generalized beyond the evidence and scope of the exercise.
