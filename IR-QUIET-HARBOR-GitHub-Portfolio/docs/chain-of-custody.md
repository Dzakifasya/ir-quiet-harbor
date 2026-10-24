# Chain of Custody — Sanitized Example

## Purpose

A chain-of-custody record documents who collected, handled, transferred, stored, and analyzed evidence. It helps establish continuity and makes later review possible.

This file describes the process principles used in an academic simulation. It is not a signed legal record and does not include real personal details or evidence identifiers beyond generalized labels.

## Minimum record fields

| Field | What to document |
|---|---|
| Case reference | Unique case identifier |
| Evidence ID | Unique label assigned to each item |
| Description | Neutral description of the item |
| Collection date/time | Include time zone and source clock where relevant |
| Collector | Authorized role or identifier |
| Acquisition method | Tool, version, and relevant settings where available |
| Integrity value | Hash algorithm and digest, stored in the restricted record |
| Seal/storage | Packaging, seal number, and storage location |
| Transfer history | Date/time, releasing and receiving parties, purpose, and signatures |
| Exceptions | Damage, clock offset, hash mismatch, or other deviations |

## Example transfer log

| Event | Released by | Received by | Purpose | Record status |
|---|---|---|---|---|
| Initial transfer | First responder | Evidence custodian | Secure storage | Record in case file |
| Analyst checkout | Evidence custodian | Authorized analyst | Examination of a working copy | Record in case file |
| Return | Authorized analyst | Evidence custodian | Return and archival storage | Record in case file |

## Good practice

- Record each custody transfer as it occurs.
- Use a trusted time reference and document time-zone information.
- Obtain acknowledgements from both releasing and receiving parties.
- Keep source evidence protected and distinguish it from working copies.
- Record integrity checks and every exception.
- Restrict access to detailed custody records where they contain personal or operationally sensitive data.

## Scope note

The table above is a generalized example, not a claim that this repository contains a signed or independently audited chain-of-custody record.
