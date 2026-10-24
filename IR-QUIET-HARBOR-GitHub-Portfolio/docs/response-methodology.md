# First-Response Methodology

## 1. Authority, scope, and coordination

Before acquiring evidence, confirm written authorization and define the scope of systems and data that may be examined. Coordinate with the appropriate legal, human-resources, and incident-response stakeholders when the scenario involves a potential insider. Keep actions proportionate to the authorized scope.

**Why it matters:** A technically sound acquisition can still be compromised if authority, scope, or handling decisions are not documented.

## 2. Avoid premature confrontation

The simulation favored coordinated response over an immediate confrontation. This reduces the risk of avoidable evidence destruction while keeping response actions controlled and documented.

## 3. Order of volatility

The exercise applied order-of-volatility reasoning by prioritizing memory and process-related information before relying solely on less-volatile disk artifacts.

**Operational principle:** Preserve volatile evidence promptly when feasible, document the tools and actions used, and recognize that live acquisition itself can alter system state.

## 4. Record clock drift without changing the source clock

The host clock and trusted reference time were recorded as separate observations. The original host clock was not changed. The measured offset was then considered during timeline reconstruction.

**Operational principle:** Preserve original timestamps and document any normalized or corrected timestamps separately, including the calculation and assumed direction of the offset.

## 5. Handle removable media carefully

The simulated response documented the media in place, packaged it appropriately, recorded custody, and examined it through a write blocker.

**Operational principle:** Minimize changes to source evidence, document each transfer of custody, and record the identity of each handler, date/time, purpose, and seal condition.

## 6. Correlate rather than over-rely on one artifact

The analysis considered proxy activity, file-share auditing, device logs, process information, memory strings, and removable-media contents as a combined evidence set.

A command line can indicate an attempted or configured action, but it does not alone prove successful completion. Corroborate process evidence with network and other relevant logs.

## 7. Document uncertainty

One process-list artifact did not match the acquisition manifest's hash and size. The discrepancy was recorded and the artifact was treated cautiously. The available evidence did not establish the cause of the mismatch with certainty.

This is a key reporting practice: state what is known, what is inferred, and what remains unresolved.
