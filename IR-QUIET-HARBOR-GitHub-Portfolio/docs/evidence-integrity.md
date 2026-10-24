# Evidence Integrity Review

## Summary

In the simulation, one process-list artifact was received with a SHA-256 digest and file size that differed from the values recorded in the acquisition manifest. The other listed evidence items were reported as matching their manifest values.

The public portfolio intentionally omits the raw digest values and source file metadata.

## Why the mismatch matters

A hash mismatch means the received file is not byte-for-byte identical to the file represented by the manifest digest. A size mismatch is an additional discrepancy that should be recorded. Neither discrepancy, by itself, establishes why the change occurred or proves malicious tampering.

## Handling approach

1. Identify the artifact by evidence ID.
2. Record the expected and observed integrity values in the restricted case record.
3. Preserve the original acquisition material where available.
4. Create and label a working copy for analysis rather than silently replacing the source.
5. Recompute and record hashes for copies as appropriate.
6. Correlate findings with independent evidence sources.
7. Clearly state the limitation in the report and avoid relying on the affected artifact as the sole basis for a conclusion.

## Conclusion

The exercise submission correctly identified the problematic evidence item and supplied its actual SHA-256 value to the evaluator. The recorded evaluation awarded full credit for evidence integrity.

The reason for the discrepancy should not be asserted beyond what the evidence supports. The exercise materials describe a possible save/reformatting change, but the public-facing summary avoids treating that explanation as independently proven.

## General lesson

Integrity verification is not a box-checking exercise. A mismatch must trigger documentation, source preservation, validation of working copies, and careful interpretation.
