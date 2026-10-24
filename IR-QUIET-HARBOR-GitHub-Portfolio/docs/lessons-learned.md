# Lessons Learned

## Outcome

The exercise evaluator recorded **100/100 (Grade A)** across first-response decisions, evidence analysis, and evidence integrity. This is the score for the academic simulation, not a professional certification.

## Lessons

### 1. Coordinate before acting

Potential insider incidents require controlled coordination and clear authority. Avoid unnecessary confrontation, and ensure response actions remain within the approved scope.

### 2. Preserve volatile evidence early

Memory and process context may contain information that is absent from disk artifacts. Prioritize acquisition based on volatility, feasibility, and the risk that evidence may disappear.

### 3. Treat time as evidence

A system clock can drift. Record the host and reference times, calculate the offset transparently, preserve original timestamps, and label adjusted times as normalized values.

### 4. Correlate independent sources

A strong timeline emerges from multiple sources with different failure modes. Network logs, file access auditing, device events, process data, and memory artifacts should be compared rather than interpreted in isolation.

### 5. Make integrity exceptions visible

The process-list artifact's hash and size mismatch was a central lesson. Record the discrepancy, protect the source, analyze a clearly identified working copy, and avoid overstating what the artifact proves.

### 6. Separate observations from conclusions

For example, evidence that a transfer utility was invoked is not by itself proof that all data reached the destination. Distinguish direct observations, corroborated findings, and unresolved hypotheses.

## Improvement opportunities

- Use a standardized acquisition checklist and evidence naming convention.
- Record tool versions, command lines, time zones, and acquisition start/end times consistently.
- Automate manifest generation and post-acquisition hash verification.
- Maintain a clear distinction between original evidence and working copies.
- Include explicit confidence and limitations in the final report.
- Review sensitive-data handling before sharing case materials publicly.

## Reference guidance

Relevant frameworks for further study include RFC 3227, NIST SP 800-86, NIST SP 800-61 Rev. 3, and ISO/IEC 27037. Consult the current official editions when applying them in a real environment.
