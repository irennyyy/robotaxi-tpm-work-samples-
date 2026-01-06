# Case A — PRD (Signal-out / Blackout Robustness)

## 1) Context & scope 
- Scenario: signals dark/flashing/abnormal; city-scale outage causing multiple intersections to fail.
- Goal: stay within safety boundaries while preventing indefinite stalling/blocking, with executable degrade-and-recover.


## 2) Users & stakeholders
riders, ops/dispatch, RA, safety/validation, city/regulators (comms needs).

## 3) Functional requirements (MVP) 
### Vehicle-side 
FR1: Detect signal-out before intersection decision and switch policy.

FR2: Do not remain in conflict zones; beyond threshold, exit conflict zone or pull over.

FR3: Tiered fallback: reroute/turn-around (if safe) → pull over → RA → terminate as last resort.

### Service & ops 
FR4: RA is scarce: only trigger when automation cannot resolve with a clear remedy; support queuing/timeouts.

FR5: Fleet anomaly detection: grid-aggregate event density; recommend ops actions (shrink/pause/recall).

FR6: Rider messaging: reason, expected handling, options (wait/cancel/reassign).

### Auditability
FR7: minimum logs: timestamp, location, mode switch, wait reason, fallback path, RA status, final outcome.

## 4) Non-goals 
- No perception/planning algorithm or training details.
- No promise of uninterrupted service; degradation/pausing is acceptable.


## References 
- Waymo help (general operability context): https://support.google.com/waymo/answer/9696059

